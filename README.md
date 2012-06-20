dirtopdf
========

Given a directory of TIFFs, generate a web-friendly PDF.

See the comments at the head of the script for usage. You may need to fiddle
with the convert command around line 104, especially wrt `-density` and 
`-quality`.

The basic process is to loop over the TIFFs, making a bunch of one-page PDFs in
a temporary directory, and then join them together at the end. The advantage 
of this extra effort as opposed to, e.g.:

	convert $DIR/*.tif -compress JPEG -density 96x96 -quality 80 $out/my.pdf

is that it is much less resource intensive.

