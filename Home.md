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
![image](https://github.com/Hillobar/Rope/assets/63615199/137badd0-eee3-4101-bc51-ba453caeabca)

* First time use:
 1. Select your Source Faces Folder
 2. Select your Target Videos Folder
 3. Select your Output Folder
 4. Click Start Rope
* Subsequent uses 
 4. Click Load Folders. 1, 2, and 3 will be remembered from the last time Rope was used.
* Models are only loaded when you initialize them the first time. GFPGAN, CLIP, Occluder, and Mouth Parser are not loaded into memory until you click them. If you have lower memory, you should be able to now run more threads if you don't enable them.

