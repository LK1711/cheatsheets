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
