# ImageMagickVisRef

A visual reference

Here's the dude  
![a](images/dude.png)  
I want to chop dude.png into frames  
`convert <in>.png -crop <height>x0 <out>%02d.png`  
in this case I know dude <in> is 32px high.  
So type in convert, drag in dude, continue, drag in the output location +file naming convention.

so the exact cmd was  
`$ convert ~/dude-cropped.png -crop 32x0 /out/d%02d.png`  
![a](images/d04.png)  

---  
</br>

heres the source sprite sheet  
![a](/images/bobs.png)  
crop source img into rows. I saw dimensions in Finder and divided pixel height by number of rows, counted. so it's like "-crop to px <rightmost>x<lowest>"  
then  
`convert bobs.png -crop 0x32 ../bobrows/b%02d.png`  
to get 19 rows  
![a](images/b00.png)  
![a](images/b01.png)  
go into results folder (but unneeded). Use bracket expansion to target a number range of named files. in this case we need to split it as {00..19} wont work.  
`cd bobrows`  
`convert b0{0..9}.png -crop 32x0 ../bobtiles/c%03d.png`  
Produces  
![a](images/c028.png)  
`convert b1{0..9}.png -crop 32x0 ../bobtiles/d%03d.png`  
![a](images/d198.png)
![a](images/d199.png)
