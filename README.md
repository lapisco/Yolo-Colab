Training Yolo-v2 on Colab
===

This repository explains how to run the notebook to train Yolo inside a Colab notebook. It save the weights hourly makeing it easy to resume from a previous checkpoint.

# How tu use it

## 1. Setup data

The data should be a `.zip` file containing the following strucutre

    ├── data.zip
        ├── cfg     <-  configurations files for yolo (more details below)
        ├── img     <-  Image files .png or .jpg, etc, and the .txt     with markers

The `cfg` directory should contain:
- `obj.data`: the path for the `train.txt` file;
- `obj.names`: the labels for the in the dataset;
- `test.txt`: the path wherein the training images are stored;
- `train.txt`: the path wherein the test images are stored;
- `yolo-v2.cfg`: last, but not least, the main file to use during training call of YoLo. See more in [AlexeyAB](https://github.com/AlexeyAB/darknet/tree/master/cfg).

The `img` directory is pretty straightfoward. 

### 1.1 Generating `train.txt` and `test.txt`

To generate these files use the magical script created by [leandrobmarinho](https://github.com/leandrobmarinho/), named of [write_img_names.py](https://github.com/leandrobmarinho/yolo-marker/blob/master/write_img_names.py). Take a look in his repo, as well as, star him :)

# Using the notebook [Cloud_Yolo_Train](Cloud_Yolo_Train.ipynb)

- GLOBAL CONFIGURATIONS

```python
DATAFILE_ID = '1UUScyA913_iWAZsS8wWgG0pAeMflAbZ-'
OUTPUT_FOLDER_ID = '1h6tpmWqPd8nVd-4bc8xNPKehf-JBvm54'
FINETUNING = False
RESUME_TRAINING = True
CHECKPOINT_FILE_ID = '1MSSs76SKJeg7v0oBkf61kDuSGyUF4zxC'
WEIGHTS_FILE_NAME = 'yolo-v2_final.weights'
``` 

- `DATAFILE_ID`: The ID you outta get of you `zip` folder into drive.
- `OUTPUT_FOLDER_ID`: The ID you outta get of you `zip` folder you desired to save the output files.
- `FINETUNING`: that's what it is.
- `RESUME_TRAINING`: set to false when you want to train from scratch.

>  **WARNING**: If you set `RESUME_TRAINING` to True you must upload the `.weights` from which you want to resume your training. 

- `CHECKPOINT_FILE_ID`: the id of the uploaded weights.
- `WEIGHTS_FILE_NAME`: the file name of these weights.set to false when you want to train from scratch.

There is nothing to worry about the rest. Run the following cell as you scroll down and the traning should start and upload `.weights` to the `OUTPUT_FOLDER_ID`.

> Keep in mind to accept drive permissions and authenticate it.
