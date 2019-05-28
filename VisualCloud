#Visual Cloud Lab user guide

## Preparation: Running docker and cp mp4 file to test
> In this task you will review the server configuration, and learn how to adjust the core speeds manually
> You will also learn how the core mappings are unique to each CPU chip
1. Launch the pre-intall the docker instance
```
 docker run -v “$PWD:/mnt:ro” -it openvisualcloud/xeon-centos76-media-ffmpeg /bin/bash
```
2. Change directory to current
```
 cd
```
3. Copy sample mp4 file to current directory
```
cp /mnt/*.mp4 .
```

## FFmpeg basics:
```
ffprobe -v error -show_streams travel6.mp4
ffmpeg -i travel6.mp4 -c:v rawvideo -pix_fmt yuv420p travel6.yuv
``` 

## SVT-HEVC encoding:
```
SvtHevcEncApp -i travel6.yuv -w 1920 -h 1080 -b travel6_hevc.ivf .
ffprobe -v error -show_streams travel6_hevc.ivf
```
```
ffmpeg -i travel6.mp4 -c:v libsvt_hevc travel6_hevc.mp4
ffprobe -v error -show_streams travel6_hevc.mp4
```

## SVT-AV1 encoding:
```
SvtAv1EncApp -i travel6.yuv -w 1920 -h 1080 -b travel6_hevc.ivf .
ffprobe -v error -show_streams travel6_av1.ivf
```
```
ffmpeg -i travel6.mp4 -c:v libsvt_av1 travel6_av1.mp4
ffprobe -v error -show_streams travel6_av1.mp4
```

## End of the lab
