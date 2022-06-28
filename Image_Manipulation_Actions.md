Allows the scaling of images from within Quicksilver.

Use the "scale image" action and give it text in the form:

-   "SCALE_INFO \[as FORMAT_INFO\]"
-   SCALE_INFO: "\[fit\] WIDTH \[x HEIGHT\]"
-   FORMAT_INFO: "JPG/PNG/GIF/TIFF \[low/med\*/hi\*\] \[prog(ressive)\]
    \[inter(laced)\]"

Examples:

-   "fit 640x480 as jpg high progressive" - creates an image that will
    fit within a 640x480 rectangle
-   "50% as interlaced png" - creates a png with dimensions half of the
    original"
-   "x72 as gif" - makes a gif 72 pixels tall, with width to maintain
    the proportions

Addressed comprehensively on page 110 of [Howard Melman's
Manual](http://mysite.verizon.net/hmelman/Quicksilver.pdf).