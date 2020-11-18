# praxinoscope
This project allows creating new custom animation discs for toy praxinoscopes.
I bought such a toy for my son, it is sold with a set of black-and-white paper discs with various small animations.
One of the discs is a blank one, on which you're supposed to draw your own cartoon.
I wanted to go further, and use a computer to design my own discs.

# "hardware" compatibility
The discs are custom sized for my son's toy
Though, all dimensions are configurable, so the discs could be adapted to any different-sized similar praxinoscope. If you have such a different praxino, let me know about it.

# Quick Sample
To see a sample, download the pdf file from this repository.
You can simply print, cut, and use with your own praxinoscope.
Be sure to disable any resizing while printing.

# Requirements
You need to install "ghostscript" tool on your machine

# easy use
- Choose your own gif or video and open it in Gimp (or other image editor of your choice)
- Reduce the animation to 9 frames, and export them as jpeg format
- Create a new subfolder in "frames"
- Put your 10 frames in this folder, with names 000.jpg to 009.jpg
- Edit praxino_simple.ps text file
   modify the second last line : 21 2 div 18  2.2 (panther) 480 270 (image) 1 drawPraxino
   change "panther" to your subfolder name
   change "480 270" to your images width and height
   "2.2" represents the distance between the center of the disc and start of the image. The images will be resized accordingly.
   Either leave it as 2.2, or fine tune for your preferred result
- Save the file and run the converter script named "convert_praxino.ps_to_pdf"
   (for windows : .bat version, for linux : .sh version)
- That will invoke ghostscript and generate the target pdf
- Open praxino_simple.pdf, print, cut, and use

# advanced use
Open praxino.ps file.
Usage is explained in the comments.
You might read some basics about postscript, though. Specifically, RPN notation.
To use images, create a subfolder under 'frames', and name your images 000.jpg to 009.jpg
For the sample, I selected some GIFs which I converted to jpeg frames.
You can also use a personal video as input.
Though, limited to 10 frames because of praxinoscope 'hardware'

# how to generate PDF
Some printers are able to directly print from a ps file.
Though, it's way easier to generate a PDF.
You need to install ghostscript tool for this.
A batch script (for Windows) and shell script (for Unix) are both provided.
Run it, and it will convert praxino.ps to praxino.pdf

# share !
If you can create fun discs with this tool, please share them !

# technical solution
I chose to model the disc structure with postscript language, because I wanted something simple with vector output, precise output measurements and bitmap pictures integration. I know that SVG could also have been an option. 
