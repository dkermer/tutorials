---
title: "Testing Coffee"
date: 2020-04-20T21:34:54-04:00
draft: false
tags: ["One", "Two"]

---

Description 

<!--more-->



## Box Types

{{% note %}}
This is a note! It's something the reader may like to know about but is supplementary to the main content. Use notes when something may be interesting but not critical.
{{% /note %}}

{{% warning %}}
This is a warning! It's about something the reader should be careful to do or to avoid doing. Use warnings when something could go wrong.
{{% /warning %}}



## Code


{{<code numbered="true">}}
<div [[[role="dialog"]]] [[[aria-labelledby="dialog-heading"]]]>
  <button [[[aria-label="close"]]]>x</button>
  <h2 [[[id="dialog-heading"]]]>Confirmation</h2>
  <p>Press Okay to confirm or Cancel</p>
  <button>Okay</button>
  <button>Cancel</button>
</div>
{{</code>}}

{{<cmd>}}
npm run start
{{</cmd>}}



## Expandable Section

{{< expandable label="A section of dummy text" level="2" >}}
Here is some markdown including [a link](https://twitter.com/heydonworks). Donec erat est, feugiat a est sed, aliquet pharetra ipsum. Vivamus in arcu leo. Praesent feugiat, purus a molestie ultrices, libero massa iaculis ante, sit amet accumsan leo eros vel ligula.
{{< /expandable >}}

## File Tree

{{% fileTree %}}
* Level 1 folder
    * Level 2 file
    * Level 2 folder
        * Level 3 file
        * Level 3 folder
            * Level 4 file
        * Level 3 folder
            * Level 4 file
            * Level 4 file
        * Level 3 file
    * Level 2 folder
        * Level 3 file
        * Level 3 file
        * Level 3 file
    * Level 2 file
* Level 1 file
{{% /fileTree %}}



## Refer to another Article

I can reference the {X{% pattern "Character Encoding" %}X} pattern here.
But it has to be in the patterns folder. 