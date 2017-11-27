### "detector test" VS "detect" 

"detector test" allows you to select appropriate configuration setup (.data file)

``` 
./darknet detector test cfg/voc.data cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights foto.jpg 
``` 

Whereas, "detect" runs predefined .data files in the background

```
./darknet detect cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights foto.jpg 
```

### Run YOLO to detect VOC objects (20 classes: person, etc)

```
./darknet detector test cfg/voc.data cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights foto.jpg 
```
