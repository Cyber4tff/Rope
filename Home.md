# Overview
![image](https://github.com/Hillobar/Rope/assets/63615199/7b27274b-aa56-401f-8d74-d0172a4f30a5)

# How to - 
## Install
Note: It's only configured for CUDA (Nvidia)
### Reuse Rope-Space Worm venv Install
* Go to your current Rope-Space Worm directory
* Delete everything except the venv directory, and the [GFPGANv1.4.onnx](https://github.com/Hillobar/Rope/releases/download/Space_Worm/GFPGANv1.4.onnx), [inswapper_128_fp16.onnx](https://github.com/Hillobar/Rope/releases/download/Space_Worm/inswapper_128.fp16.onnx), and [occluder.ckpt](https://github.com/Hillobar/Rope/releases/download/Space_Worm/occluder.ckpt) model files
* Copy in Rope-Crystal files. You should have Rope.bat, requirements.txt, and Rope.py files, and models, rope, and venv folders in this directory, along with the model files
* Download [79999_iter.pth](https://github.com/Hillobar/Rope/releases/download/Crystal/79999_iter.pth) and [epoch_16_best.ckpt](https://github.com/Hillobar/Rope/releases/download/Crystal/epoch_16_best.ckpt) model files
* Move the model files ([GFPGANv1.4.onnx](https://github.com/Hillobar/Rope/releases/download/Space_Worm/GFPGANv1.4.onnx), [inswapper_128_fp16.onnx](https://github.com/Hillobar/Rope/releases/download/Space_Worm/inswapper_128.fp16.onnx), [occluder.ckpt](https://github.com/Hillobar/Rope/releases/download/Space_Worm/occluder.ckpt), [79999_iter.pth](https://github.com/Hillobar/Rope/releases/download/Crystal/79999_iter.pth), and [epoch_16_best.ckpt](https://github.com/Hillobar/Rope/releases/download/Crystal/epoch_16_best.ckpt)) to the models directory
* Double-click on Rope.bat!

### Clean Install
* Copy Github files to a local directory
* Navigate to the Rope main directory (you will see requirements.txt, Rope.bat, Rope.py, and two folders)
* Right click and select 'Open in Terminal' (or open CMD and navigate there)
* Set up a local venv
  * python.exe -m venv venv
* Activate your new venv
  * .\venv\Scripts\activate
* Install requirements
  * .\venv\Scripts\pip.exe install -r .\requirements.txt
* Place [GFPGANv1.4.onnx](https://github.com/Hillobar/Rope/releases/download/Space_Worm/GFPGANv1.4.onnx), [inswapper_128_fp16.onnx](https://github.com/Hillobar/Rope/releases/download/Space_Worm/inswapper_128.fp16.onnx), [occluder.ckpt](https://github.com/Hillobar/Rope/releases/download/Space_Worm/occluder.ckpt), [79999_iter.pth](https://github.com/Hillobar/Rope/releases/download/Crystal/79999_iter.pth), and [epoch_16_best.ckpt](https://github.com/Hillobar/Rope/releases/download/Crystal/epoch_16_best.ckpt) in the models\ folder
* Do this if you've never installed roop or Rope (or any other onnx runtimes):
  * Install FFMPEG
  * Install CUDA Toolkit 11.8
  * Install dependencies:
  * pip uninstall onnxruntime onnxruntime-gpu
  * pip install onnxruntime-gpu==1.15.1
* Double-click on Rope.bat!

## Startup
![image](https://github.com/Hillobar/Rope/assets/63615199/137badd0-eee3-4101-bc51-ba453caeabca)

* First time use:
 1. Select your Source Faces Folder
 2. Select your Target Videos Folder
 3. Select your Output Folder
 4. Click Load Folders
* Subsequent uses 
 4. Click Load Folders. 1, 2, and 3 will be remembered from the last time Rope was used.
* Models are now only loaded when you initialize them the first time. GFPGAN, CLIP, Occluder, and Mouth Parser are not loaded into memory until you click them. If you have lower memory, you should be able to now run more threads if you don't enable them.

## Swap
![image](https://github.com/Hillobar/Rope/assets/63615199/adbd042f-0a7b-4d3a-9f36-674d502965c3)

1. Select a Target Video (mousewheel scroll the Target Videos)
2. Move to a video frame with faces in it and click Find
3. Select a found Target Faces (mousewheel scroll the Target Faces)
4. Select a Source Face (hold shift to select multiple Source Faces), (mousewheel scroll the Source Faces), (mousewheel scroll in the Video Player to iterate through the Source Faces)
5. Click Swap

##  Source Face Shortcut
![image](https://github.com/Hillobar/Rope/assets/63615199/5aaebe15-5709-4101-a0ba-5cf4ac2f54ee)

* Create
1. Select a Source Face (hold shift to select multiple Source Faces)
2. Type in a name, hit enter
* Delete
3. Select a Source Face Shortcut
4. Click Delete

## Record/Play
![image](https://github.com/Hillobar/Rope/assets/63615199/0ba825f5-dcb6-4f9a-a3a6-66d780dc0c78)

1. Arm/Disarm Record
2. Play. If Record is armed, then it will record and save to the Output folder
  * Press Play again to stop Playing or Recording

## Merge Source Faces
* Select multiple Source Faces by holding down shift
  * Selecting multiple, different images of the same person can improve likeness.
  * Selecting different people will create an average of the selected faces

# Interface Options
## Face Options
### GFPGAN
<img src="https://github.com/Hillobar/Rope/assets/63615199/a9eda3b0-1106-4213-9ea4-1e146e7e3ddd" width="150">

* Increases the resolution of the Face
* Click to toggle on/off. Scroll the mousewheel to change the strength (0% = off, 100% = full strength)

### Difference
<img src="https://github.com/Hillobar/Rope/assets/63615199/0d54ab59-c284-4249-b50e-76b1969aa189" width="150">

* Allows areas of the Target Face to show where the Target Face and swapped face are similar
* Click to toggle on/off. Scroll the mousewheel to change the threshhold (0% = very strict, 100% = no restrictions)

### Top Mask
<img src="https://github.com/Hillobar/Rope/assets/63615199/92115f8c-b659-4db1-b6c8-b6be0e0232a6" width="150">

* Lowers and Raises the mask boundary at the forehead
* Scroll the mousewheel to lower and raise the position  (0% = boundary at top, 100% = boundary in the middle of the face)

### Mask Blur
<img src="https://github.com/Hillobar/Rope/assets/63615199/6f94e9d1-4843-430e-93b0-f502e7749f64" width="150">

* Sets the amount of blur for the Top Mask (and consequently Side Masks)
* Scroll the mousewheel to change the strength (0% = no blur, 100% = high blur)

### CLIP
<img src="https://github.com/Hillobar/Rope/assets/63615199/12b9578a-cd8f-45f6-818e-970ef94e0ddd" width="150">

* Create masks based on text input
* Enter text in field separated by commas. E.g., cup,hand
* Click on CLIP button to toggle on/off
* Scroll the mouse wheel to adjust word strength (higher is stronger)

### Occluder
<img src="https://github.com/Hillobar/Rope/assets/63615199/fd4a0d96-f3f7-4e9d-8407-c8c20d80f5a2" width="150">

* Creates a mask of any objects that occlude the face. Good for auto masking hair. Not good for profile.
* Click to toggle

### Mouth Parser
<img src="https://github.com/Hillobar/Rope/assets/63615199/c0e5ecb4-2894-4593-86ba-24f39de588c4" width="150">

* Creates a mask around the mouth from the original face and the swapped face. Good for talking. Not good for preserving likeness.
* Click to toggle

### Threshhold
<img src="https://github.com/Hillobar/Rope/assets/63615199/a9a472c3-9246-427b-814a-bbba661d9288" width="150">

* Used by the swapper to determine if the Target Face matches any faces in the frame.
* Scroll the mousewheel to change the strength (85% default, lower is stricter, higher is less restrictive). If you are swapping two or more different Target Faces and they sometimes switch around, lower the value until they are applying correctly. Click the button to toggle applying to all faces. 

### Blur
<img src="https://github.com/Hillobar/Rope/assets/63615199/d3e203e8-4561-4c3e-bdb3-cec6b01da954" width="150">

* Sets the amount of blur for all of the masks
* Scroll the mousewheel to change the strength (0% = no blur, 100% = high blur)

## Target Faces
### Find
<img src="https://github.com/Hillobar/Rope/assets/63615199/0f3868af-1b69-4d6b-860c-7a6af6957e27" width="150">

* Finds all faces in the current frame
* Click to find faces

### Clear
<img src="https://github.com/Hillobar/Rope/assets/63615199/64b69528-db53-4d25-9570-4bd95189472e" width="150">

* Clears all Target Faces
* Click to clear faces

### Swap
<img src="https://github.com/Hillobar/Rope/assets/63615199/6896241f-11c2-4928-8848-372fc01be7bc" width="150">

* Swap all Target Faces with their assigned Source Faces
* Click to toggle Swapping on/off

## Source Faces
### Source Faces Folder
<img src="https://github.com/Hillobar/Rope/assets/63615199/43a265c1-1e69-4f67-bed2-5efd7eeb4083" width="150">

* Selects the Source Face Folder
* Click to open the file dialogue. Will automatically load the Source Faces once selected.

### Source Face Shortcut Text
<img src="https://github.com/Hillobar/Rope/assets/63615199/ee6affdf-a8fd-4db1-9147-8dd6cda079c0" width="150">

* Text field to name Source Face Shortcut
* Select Source Face (select multiple with shift). Once highlighted, name them in this text field and hit enter. The new Source Face Shortcut will be added to the Source Faces

### Source Face Sortcut Delete
<img src="https://github.com/Hillobar/Rope/assets/63615199/3885d0e9-9cc6-4543-8681-190d27ad7794" width="150">

* Deletes the selected Source Face Shortcut
* Select a Source Face Shortcut. Click the button to delete.

## Target Videos
### Target Video Folder
<img src="https://github.com/Hillobar/Rope/assets/63615199/a4ca6cf2-095a-4fba-9531-9f9f668bdffe" width="150">

* Selects the Target Videos Folder
* Click to open the file dialogue. Will automatically load the Target Videos once selected.

## Program Options
### Load Folders and Swapper
<img src="https://github.com/Hillobar/Rope/assets/63615199/fee2b645-1cdb-461e-adb7-f66442bf4adb" width="150">

* Loads up all the necessary data to start swapping
* Click to load. Loads in Target Videos, Source Faces, and the Swapper model

## Changelog ##
### Changes for Rope - Space Worm: ###
* Updated video rendering to use Target Video parameters
* Mousewheel scroll on the time bar to control frame position
* Added an occluder model (experimental, very fast, make sure you download the new model-link below)
* Greatly increased performance for larger videos/multiple faces
* CLIP crashing fixed. Add as many words as you like!
* Detachable video preview
* Fixed most bugs related to changing options while playing. Adjust setting on the fly!
* GFPGAN now renders up to 512x512
* Status bar (still adding features to this)


