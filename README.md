# debugging

# Moviepy and ImageMagick problem:

If you are using TextClip feature in moviepy, then you would notice a problem like this:

IOError: MoviePy Error: creation of None failed because of the following error:

convert: not authorized `@/tmp/tmp4d2miI.txt' @ error/property.c/InterpretImageProperties/3307.
convert: no images defined `PNG32:/tmp/tmp5TBBnp.png' @ error/convert.c/ConvertImageCommand/3210.
.

.This error can be due to the fact that ImageMagick is not installed on your computer, or (for Windows users) that you didn't specify the path to the ImageMagick binary in file conf.py, or.that the path you specified is incorrect


In order to solve the problem, you would need to change ImageMagick configuration. The configuration is stored in /etc/ImageMagick-6 folder in my machine


The file is policy.xml


You search for a pattern that says "@*" and you replace "none" in the rights attribute to "read | write".

And, that's it.


[YouTube link](https://www.youtube.com/watch?v=HZh0VTo6q-Y)
