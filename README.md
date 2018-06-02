# ImageMagickVisRef

A visual reference

To crop a sprite sheet  
![a](/images/bobs.png)  
do this
> `convert bobs.png -crop 32x32 +repage d%03d.png`

Produces  
![a](images/c028.png)

---
Tips:  
Convert to gif before cropping to see the whitespace that pngs hide.  
Output %03d cos it probably generates 100s of sprites.
I probably do want to keep the rows anyway!

---

</br>


Here's the dude. I want frames.  
![a](images/dude.png)  
First convert png to gif to see whitespace better.
> `convert dude.png dude.gif`  

the syntax to crop is a bit like this:  
> `convert <in> -crop <w>x<h> +repage <out>%02d.png`

In this case I know dude is 32px wide. So type "convert", drag in dude, continue, drag in the output location +file naming convention.

so the cmd was

> `convert ~/dude-cropped.png -crop 32x0 +repage d%02d.png`

![a](images/d04.png)

---
source sprites
![a](images/d019.gif) ![a](images/d120.gif) ![a](images/d121.gif)  
append in a row
>`magick d019.gif d120.gif d121.gif +append tv1.gif`

![a](images/tv1.gif)

append in a stack  
>`magick d019.gif d120.gif d121.gif -append tv1.gif`

![a](images/tv2.gif)

---

source  

> `magick d00%d.gif[0-7] bl.gif`
