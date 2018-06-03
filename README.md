## ImageMagickVisRef

### A visual reference

---

Generate a builtin image
>`magick rose: rose.gif`

![a](images/rose.gif)  

---

convert png to gif (to see whitespace better)
> `convert dude.png dude.gif`  

---

To crop a sprite sheet  
![a](/images/bobs.png)  
do this
> `convert bobs.gif -crop 32x32 +repage d%03d.gif`

Produces  
![a](images/c028.png)

---

Rows

---

</br>


Here's the dude. I want frames.  
![a](images/dude.png)  

In this case I know dude is 32px wide

> `convert ~/dude-cropped.png -crop 32x0 +repage ~/d%02d.png`

![a](images/d04.png)

---
source sprites
![a](images/d019.gif) ![a](images/d120.gif) ![a](images/d121.gif)  
append in a row
>`magick d009.gif d010.gif d011.gif +append tv1.gif`

![a](images/tv1.gif)

Can also do above based on filename number!

>`magick d%03d.gif[9-11] +append tv1.gif`

append in a stack  
>`magick d1.gif d2.gif d3.gif -append tv1.gif`

![a](images/tv2.gif)

---


For offset, the origin (0,0) is upper-left corner. (w)x(h)(+right)(+down)  
The following negatively colours a (tall) area:  
First in topL corner 10px to the right, 20px down. turned a red rose blue
>`magick rose: -region '100x200+10+20' -negate rNeg1.gif`

![a](images/rNeg1.gif)

This spills off the left edge
>`magick rose: -region '100x200-10+20' -negate rNeg2.gif`

![a](images/rNeg2.gif)

This resets the origin (0,0) to the centre so offset is below+L of it.
>`magick rose: -gravity center -region '100x200-10+20' -negate rNeg3.gif`

![a](images/rNeg3.gif)

dead centre
>`magick rose: -gravity center -region '100x200' -negate rNeg4.gif`

![a](images/rNeg4.gif)

---

source  
Make a gif

> `magick d00%d.gif[0-7] bl.gif`

</br>

---

Tips:  
Convert to gif before cropping to see the whitespace that pngs hide.  
Output %03d cos it probably generates 100s of sprites.
I probably do want to keep the rows anyway!


