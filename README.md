# basicrop
Basic cropping script.

Dependencies:
- feh
- hacksaw
- sxhkd
- graphicsmagick
- bc

These deps can be easily replaced with other programs. `hacksaw` can be replaced with `slop`, `gm convert` (for `graphicsmagick`) with `convert` (for imagemagick), or `feh` with `nsxiv` (with some argument tweaking). It's a very simple script, with the most complex part being some multiplication.

## instructions
Set screen dimensions in the file (default is 1920x1080).

Arg 1 is input file, arg 2 is output. If output isn't specified, the input will always be overwritten.
- 'c' to crop
- 'u' to undo
- 'A' to toggle anti-aliasing
- 'Escape' or 'q' to quit
- 'Return' to save file
- 'shift' + 'Return' to overwrite file

Because there's no way to communicate the image's location to the script, you cannot zoom in or translate.

## how work?
`basicrop input output` will open `input` in fullscreen mode. With your screen dimensions, this acts like a ruler by constraining the sides of your image to the sides of the screen. Cropping will simply take the dimensions of the screen captured in an area, and scale it up or down to the size of the image. Those dimensions are trimmed if needed, and then fed to graphicsmagick to produce `output`.

sxhkd is used to temporarily steal a set of keys from your keyboard to use for the script. I'm sure there's a way to do it with more simple X tools, but if i wanted to make this more of a PITA then i would've make a Real image editor in C, with zooming and translating and drawing and such. But i didn't feel like it

## why?
I had all the tools already on my system, as well as a brand new screenshot script in need of a dedicated editor. In fact, this script used to be embedded into that screenshot script until i decided to debloat it and share it elsewhere. 

In the future i plan on making another editor, with a similar feature count to `flameshot`'s editor (markup stuff), but keyboard-driven and with better image viewing, like with zooming and moving. Such a minimal standalone editor doesn't really exist right now.
