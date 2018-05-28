# twitchslam

A toy implementation of SLAM written while livestreaming.

<img width=300px src="https://raw.githubusercontent.com/geohot/twitchslam/master/demo.png" />

Stream
-----

https://www.twitch.tv/tomcr00s3

Usage
-----

```
export D2D=1       # 2-D viewer
export D3D=1       # 3-D viewer
export REVERSE=1   # Hack for reverse video
export F=500       # Focal length (in px)

./slam.py <video.mp4>

# an example from the repo
D2D=1 REVERSE=1 F=650 D3D=1 ./slam.py videos/test_countryroad_reverse.mp4 
```

Libraries Used
-----

* SDL2 for 2-D display
* cv2 for feature extraction
* pangolin for 3-D display
* g2opy for optimization (soon!)

TODO
-----

* BUGFIX: Why is window initting small?
* Add optimizer for F
* Stop using essential matrix for pose estimation once you have a track
 * Add kinematic model
 * Run g2o to only optimize the latest pose
* Add search by projection to refind old map points
 * Check if points are in the field of view of the camera
* Improve init to not need REVERSE environment variable
* Add multiscale feature extractor
