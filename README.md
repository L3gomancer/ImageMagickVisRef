# ImageMagickVisRef
A visual reference


so I want to chop dude.png into frames
convert <in>.png -crop <h>x0 <out>%02d.png
in this case I know dude <in> is 32px high <h>. type convert, drag in dude, finish command, drag in the output location +file naming convention.

so the exact cmd was
$ convert /Users/Ed/Documents/Projects/CLILearn/MyScriptPractice/IMin/dude-cropped.png -crop 32x0 /Users/Ed/Documents/Projects/CLILearn/MyScriptPractice/IMout/d%02d.png
