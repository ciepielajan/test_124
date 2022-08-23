

# guidelines for images from local storage 


## Install
```bash
pip install label-studio
```

## demo data
### project images
```
https://drive.google.com/file/d/1WohtvWtURKnsnHMzeNzcJqrCXyL4n0_x/view?usp=sharing
```

### project nlp
```
https://drive.google.com/file/d/16C_blZUJlJQFZA9wDK68OnWtR1zr4D4W/view?usp=sharing
```


## directores tree for image
```python
main/project directory
|- data # projekt nr#
    |-images
        |-<name_file>.jpg
        |-<name_file>.jpg
        |- .....
    |-adnotations
        |-id_file.json
        |-...
|-other directors
-README.md
-other files
```

## start server with local storage
replace '/home/janek/Documents/ml-prodigy-test/' path for yours project path
```bash
LABEL_STUDIO_LOCAL_FILES_SERVING_ENABLED=true LABEL_STUDIO_LOCAL_FILES_DOCUMENT_ROOT=/home/janek/Documents/ label-studio start
```

___


#### set and check local files as defoult
```bash
export LABEL_STUDIO_LOCAL_FILES_SERVING_ENABLED=true
echo $LABEL_STUDIO_LOCAL_FILES_SERVING_ENABLED
```

#### set and check path to local files
```bash
export export LABEL_STUDIO_LOCAL_FILES_DOCUMENT_ROOT=/home/janek/Documents/ml-prodigy-test/
echo $LABEL_STUDIO_LOCAL_FILES_DOCUMENT_ROOT
```

#### path on the function
```python
def create_image_url(filepath):
    filename = os.path.basename(filepath)
    path = '/data/local-files/?d=image/'
    return f'{path}{filename}'
```