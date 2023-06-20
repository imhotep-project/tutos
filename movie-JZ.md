## How to create movies from png files?

* You have created multiple png images (maps for example) named with same prefix name and ending with "_xxxx.png" where xxxx is the number of the image.
* You can concatenate them with ffmpeg to create a movie using [Laurent Brodeau's tool climporn](https://github.com/brodeau/climporn/tree/master). Here is how to do it on Jean Zay:


1. On JZ, load the ffmpeg module:

``` 
module load ffmpeg
```

2. Install Laurent's tool from git (do it once for all):

```
git clone https://github.com/brodeau/climporn.git
pwd
```

3. Go to the directory where you have archived your png images and use the umage2mp'.sh script:

``` 
/path-where-you-installed-climporn/climporn/ffmpeg/images2mp4.sh -i imageprefixname_  -f 4
```
The -f option defines the frame rate (frame per seconds).

For more options just run the script to get its manual:

```
/path-where-you-installed-climporn/climporn/ffmpeg/images2mp4.sh 
basename: missing operand
Try 'basename --help' for more information.

USAGE: images2mp4.sh -i <common_prefix_image_files> (options)

   Available options are:
      -t: format of images (default='png')
      -h: height (pixels) of video to create (default='1080')
      -c: codec for video (default='x264)' [x264, x265, ...]
      -f: input framerate == images per second (default='25')
      -C: CRF value, 0 is lossless and 51 worse possible (default='20') [ffmpeg default=23]
      -p: preset for encoding (default='medium') [fast, medium, slow, veryslow]
      -v: video format (default='mp4') [mp4,webm,...]
      -d: frequency for dropping frames (ex: -d 2 would speed up video by 2 by dropping every other frame)
      -D: directory (path) in which to create the video if elsewhere than current directory
      -n: number of threads (default='1')
      -P: pixelized! when scaling, apply nearest point interpolation!
 ```
 
4. Copy the created mp4 file on your local machine to play it




