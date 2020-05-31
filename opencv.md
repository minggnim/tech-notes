## First uninstall installed versions of opencv
$ brew uninstall opencv

## Then install openCV 2.4
$ brew install opencv@2

Didn't do
`echo 'export PATH="/usr/local/opt/opencv@2/bin:$PATH"' >> ~/.bash_profile`

Did 
```
export LDFLAGS=-L/usr/local/opt/opencv@2/lib
export CPPFLAGS=-I/usr/local/opt/opencv@2/include
export PKG_CONFIG_PATH=/usr/local/opt/opencv@2/lib/pkgconfig
```

Then change 3rd line in `Makefile` and set
`OPENCV = 1`

Run
`$ make`

Run the analysis
```
./darknet detector demo cfg/coco.data cfg/yolo.cfg yolo.weights
```
