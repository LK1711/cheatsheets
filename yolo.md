### "detector test" VS "detect" 

#### For a single image

"detector test" allows you to select appropriate configuration setup (.data file)

``` 
./darknet detector test cfg/voc.data cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights foto.jpg 
``` 

Whereas, "detect" runs predefined .data files in the background

```
./darknet detect cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights foto.jpg 
```
#### For a set of images
1. Set the folder name in **detector.c** 
2. Create a target folder for storing the detection results
3. Set the target folder name in **detector.c**
``` 
./darknet detector test cfg/voc.data cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights 
``` 
```
./darknet detect cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights
```


### Run YOLO to detect VOC objects (20 classes: person, etc)

```
./darknet detector test cfg/voc.data cfg/tiny-yolo-voc.cfg weights/tiny-yolo-voc.weights foto.jpg 
```


### Save predictions in txt files

go to image.c

- removing the extension of the image from the filename
```
char *remove(char* mystr) {
    char *retstr;
    char *lastdot;
    if (mystr == NULL)
         return NULL;
    if ((retstr = malloc (strlen (mystr) + 1)) == NULL)
        return NULL;
    strcpy (retstr, mystr);
    lastdot = strrchr (retstr, '.');
    if (lastdot != NULL)
        *lastdot = '\0';
    return retstr;
}
```
source (https://stackoverflow.com/questions/2736753/how-to-remove-extension-from-file-name)
