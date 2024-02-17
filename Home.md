# Overview

# How to - 
## Install
Note: It's only configured for Windows/CUDA (Nvidia), and must use Python 3.10

* Copy Github files to a local directory
* Navigate to the Rope main directory (you will see requirements.txt, Rope.bat, Rope.py, and folders)
* Right click and select 'Open in Terminal' (or open CMD and navigate there)
* Set up a local venv
  * python.exe -m venv venv
* Activate your new venv
  * .\venv\Scripts\activate
* Install requirements
  * .\venv\Scripts\pip.exe install -r .\requirements.txt
* [Download the models from here](https://github.com/Hillobar/Rope/releases/tag/Sapphire). Either download the models file, which has all of the model files in it, or just grab the ones you're missing in the list.
* Unzip models.zip and place the all of the model files into the models\ folder
* Do this if you've never installed roop or Rope (or any other onnx runtimes):
  * Install FFMPEG
  * Install CUDA Toolkit 11.8
  * Install cuDNN v8.5 for CUDA 11.x from [here](https://developer.nvidia.com/rdp/cudnn-archive)
* Double-click on Rope.bat!

## Startup
* First time use:
 1. Select your Source Faces Folder
 2. Select your Target Videos Folder
 3. Select your Output Folder
 4. Click Start Rope
* Subsequent uses 
 4. Click Load Folders. 1, 2, and 3 will be remembered from the last time Rope was used.
* Models are only loaded when you initialize them the first time. GFPGAN, CLIP, Occluder, and Mouth Parser are not loaded into memory until you click them. If you have lower memory, you should be able to now run more threads if you don't enable them.

## Using
* Set your folders if needed
* Click 'Start Rope'
* Select a Video
* Scroll to a frame with faces you want to swap
* Click 'Find Faces'
* Select the Found Face
* Select an Input Face or Merged Face. This assigns it to the Found face. You can shift-click multiple Input Faces to blend them.
* Select another Found Face and assign if you have more in the frame.
* Click 'Swap'
* All done! Now you can Play/Record/Adjust/etc.

In this entry of the wiki we will discuss the setup and usage instructions for Rope.  It will guide from start to a face-swapped video.



## [](https://github.com/Hillobar/Rope/wiki#install) Installation

**Disclaimer**:
This repository is only intended for use on Windows (with Nvidia CUDA). If you're using Linux, please refer to [GitHub - aquawaves/Rope-experimental: GUI-focused roop with Linux support](https://github.com/aquawaves/Rope-experimental).



1. Clone the repository to your device:

```
git clone https://github.com/Hillobar/Rope
cd Rope
```



2. Set up a local venv 

```
# create the virtual environment
python.exe -m venv venv

# activate the local venv
.\venv\Scripts\activate

# check if you have installed the correct python version (Python 3.10.X)
python --version

# install the dependencies for Rope
.\venv\Scripts\pip.exe install -r .\requirements.txt
```

or using anaconda3

```
# create a conda venv with the correct python version
conda create -n Rope python=3.10.13

# activate the virtual environment
conda activate Rope

# install the dependencies
python -m pip install -r requirements.txt
```

**Important:**
Make sure that you install the virtual environment with the correct python version. Rope only works with with any 3.10 version, nothing older or newer than that.





3. Download and install 3rd-party dependencies
- Install the models
  
    - **To get access to all the features of Rope**, you need to [download the models from here](https://github.com/Hillobar/Rope/releases/tag/Sapphire). Either download the models file, which has all of the model files in it, or just grab the ones you're missing in the list.
  
    - Place the downloaded model files in the `Rope/models` folder
  
  

- Install the external dependencies (if you haven't done so already)
  
    - FFMPEG
      
        - [Download](https://www.ffmpeg.org/download.html) FFMPEG here
      
      
  
    - CUDA Toolkit 11.8 (needed if utilizing GPU)
      
        - Follow [these instructions](https://medium.com/geekculture/install-cuda-and-cudnn-on-windows-linux-52d1501a8805#3e72) to install CUDA Toolkit v11.8
      
        - Check if the installation was successful (run in the terminal)
          
            - `nvcc --version`
          
          
  
    - cuDNN >= v8.5 for CUDA 11.x (needed if utilizing GPU)
      
        - [Download](https://developer.nvidia.com/rdp/cudnn-archive) the cuDNN >= v8.5
      
        - Follow [these instructions](https://medium.com/geekculture/install-cuda-and-cudnn-on-windows-linux-52d1501a8805#46b1) to install cuDNN



## [](https://github.com/Hillobar/Rope/wiki#update) How to update

To update the repository to its latest version, simply navigate to the Rope directory and open the terminal.

```
# pull and apply the latest updates from Github
git fetch --all

# Reset the repository to its latest version
# local files like the venv remain untouched
git reset --hard origin/master
```



## [](https://github.com/Hillobar/Rope/wiki#startup) How to use Rope

1. Choose your target video, source and ouput directories

2. Start the Rope backend by clicking on the button `Start Rope`

3. Select the source video and template face
   
    1. Shift-click multiple template faces to use a blended version

4. Swap the face in the live editor
   
    1. Scroll to a frame with the face you want to swap
   
    2. Scan contained faces by clicking `Find Faces` 
   
    3. Select the desired face
   
    4. Click `Swap Faces` to see the changes in the video player
   
    5. (Optional) Apply filters like the Restorer module to modify the results

5. Export the video to disk
   
    1. Go to the starting frame of your clip
   
    2. Press `Record` to arm the `Play` button for recording
   
    3. Press the `Play` button to start the recording
   
    4. If satisfied, press `Play` again to stop the recording 



**Disclaimer:**
Modules like the GFPGAN, CLIP, Occluder, and Mouth Parser are not automatically loaded into memory until you activate them manually. This saves you precious memory and allows you to increase the amount of threads if you have lower memory.


