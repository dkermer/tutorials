---
title: "Display a Log of Shell Commands"
date: 2020-04-20T21:34:54-04:00
draft: false
tags: ["Teaching", "Command Line", "Bash"]
---

When teaching shell scripting, learners may get behind. Extensive output can push prior command off the screen. So, it can be useful to show a clean log of recent commands.  

<!--more-->

**Option 1**: Install the [Software Carpentry Shell Split Window](https://github.com/rgaiacs/swc-shell-split-window) Script

* Windows users have extra steps since the required tmux is not natively supported. But, there are two options to get it to work:
	* [Install msys2](https://blog.pjsen.eu/?p=440)
	* [Enable the Windows Subsystem for Linux](https://veerasundar.com/blog/2018/03/how-to-split-the-terminal-into-multiple-views-in-windows-10/)

**Option 2**: Use a separate file viewer. A good cross-platform viewer is [glogg](http://glogg.bonnefon.org/). Atom can also be set up to do this. It is important to **turn off the menus**, sidebars, spellcheck and other visual elements to take up as little room as possible. Also adjust the font size for ease of viewing. 

There are a few settings that need to be changed to make it work. Both files listed below are in your **user directory**. If you do not see them, make sure hidden files are displayed. 

1. Add the following line to **.bashrc** to update the history immediately:
		`PROMPT_COMMAND="history -a;$PROMPT_COMMAND"`
	
2. In your chosen file viewer, open  **.bash_history**

3. Set the viewer to automatically load file changes 
   
    1. In glogg, go to "View" then "Follow File"
    
    2. In Atom, go to "File" and choose "Init Script...", paste the following
    
        ```
        atom.workspace.observeTextEditors (editor) ->
           editor.onDidChange ->
             if editor.getTitle() is ".bash_history" and not editor.isModified() then editor.moveToBottom()
        ```
    
4. If you make the prompt display line numbers (see Changing the Bash Prompt), you may want to turn on those too.  The combination can be particularly helpful.  