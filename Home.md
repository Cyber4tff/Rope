# Overview
![image](https://github.com/Hillobar/Rope/assets/63615199/7b27274b-aa56-401f-8d74-d0172a4f30a5)

# How to - 
## Install
Note: It's only configured for CUDA (Nvidia)

* Copy Github files to a local directory
* Navigate to the Rope main directory (you will see requirements.txt, Rope.bat, Rope.py, and folders)
* Right click and select 'Open in Terminal' (or open CMD and navigate there)
* Set up a local venv
  * python.exe -m venv venv
* Activate your new venv
  * .\venv\Scripts\activate
* Install requirements
  * .\venv\Scripts\pip.exe install -r .\requirements.txt
* [Download the models from here](https://github.com/Hillobar/Rope/releases/tag/Sapphire). Either download the models file, which has all of the model files in it, or just grab the ones you missing in the list.
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
### GFPGAN / Codeformer
<img src="https://github.com/Hillobar/Rope/assets/63615199/a9eda3b0-1106-4213-9ea4-1e146e7e3ddd" width="150">

* Increases the resolution of the Face
* Left click to toggle on/off. Right Click to toggle GFPGAN or Codeformer. Scroll the mousewheel to change the strength (0% = off, 100% = full strength)

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
### (2023-11-17) Changelog for Rope - Sapphire: ###
**Note: Please check the wiki for installation and link to the new models file**
- Images! In addition to videos, use Rope to swap images. Seamlessly integrated into the current interface.
- Timeline markers. Add markers to the timeline that capture the current settings at a specific frame. When playing back or recording, markers control the options when the frame is reached. Add as many markers as you need!
- Iterations. Apply the swapper model multiple times to a face. It seems to increase likeliness if used carefully.
- Orientation. Sometimes faces are at a bad orientation, like laying down or upside-down. The face detector has problems with this, so Rope now has an option to tell the detector which way the face is oriented. It is also markerable, so you can set markers for it per frame!
- Tool tips on (almost) everything. Tips are in the bottom pane.
- Bug fixes and refactoring

### (2023-11-18) Bug Fixes for Sapphire - Shard: ###
- (fixed) saving the same image multiple times in a row overwrites it. the time is appended when the image is loaded, not saved, so the time is always the same
- (fixed) cf is returning weird colors, similar to when the rgm bgr stuff was messed up. try swapping rgp before netering cf
- (fixed) GFPGAN fp16 might be causing too much harm (going back to original)
- (fixed) the orientation feature might not be unorienting
- (fixed) bug (I hope :D) : When clicking on a registered face name (the one of the left) to swap, on the previous version, clicking back to the same face name would delete the choice and unswap the face. Now it's just blocked and I can't "unswap" (unselect) the face. I'm force to select a face or just close and restart the soft.
- (fixed) update text for all the parser features
- (fixed) "Switch from one timeline marker to another doesn't properly show the correct features configured. Switch to the next frame (and back the previous one is working too) will fix it and show the correct configuration actually configured on the frame."
- (fixed) update mask tooltip
- (fixed) Btw accidentially scrolling Strength below 100% crashed Rope now the third time when CF is enabled. Haven't seen this with GFPGAN yet. I can screenshot the console error if that helps...
- (new) Added Mask view button, moved mask blur to button above mask view
- (new) MouthParser scrolls in negative direction to a)only mask the inside of the mouth, and b) grow the inside mouth mask as the amount increases
- (fixed) GFPGAN and Codeformer will give better results now, especially with details around the eyes and mouth. 
- (fixed) in some cases, pixel values will be > 255
- (new) added undock button to image view
- (new) 'Strength' now has an on/off state
- (fixed) intermittent play bug
- (new) Click the mouse on the playback screen to control play/pause
- (new) Keyboard control with wasd and space 
- (new) Stop Marker. Sets a frame that will stop the video playing/recording

### (2023-12-02) Bug Fixes for Sapphire - Shard: ###
- (new) Added performance testing button. Turn on to report some stats in the console. Stats during threaded Play will be jumbled.
- (fixed) Tooltip fixes
- (fixed) Fixed bad Rope behavior when losing focus and returning  
- (fixed) Fixed crashing when using WASD on images
- (fixed) GFPGAN and Codeformer are now working correctly. This required adding another detection model to these enhancers, so performance is slightly worse now using CF and GFPGAN but the quality is better.
- (new) Rope can now undock and redock
- (new) Rope will remember window positions and sizes between sessions, for both docked and undocked views
- (fixed) Fixed multiple embedding selection bug
- (fixed) Recording with one thread works again

- ### (2023-12-04) Bug Fixes for Sapphire - Shard: ###
- (fixed) CV_64F error related to passing float64 to opencv
- (fixed) Indexerror error related to differences in detection performance between resnet50 and Retinaface

Fun Stuff:
* Added mousewheel function to Mouth Parser to adjust the size of the mask
* Added Codeformer as an enhancer option. Codeformer does a noticeably better job with skin textures, but runs slower. Right-click on the button to toggle Codeformer or GFPGAN. Note: Codeformer takes 15-30 secondfs to load the first time.

Boring Stuff:
* Mouth Parser and Occluder now use onnxruntime instead of PyTorch. Hopefully this will solve issues with AMD cpu users
* InsightFace libraries have been removed as a dependency
* Dependencies have been updated and aligned
* Performance increase
* Swapping is now automatically toggled off when dragging the timeline slider. this is to make it more responsive. It will automatically toggle the swap back on once you stop dragging if you had swap on to begin with.

Bug Fixes:
* Fixed bug when dragging the Video timeline. It can now be moved when playing
* Fixed several remaining bugs with recording 
* Fixed right click behavior on the video player slider

### (2023-09-03) Changes for Rope - Crystal: ###
* New, slightly improved GUI
* Merged Source Faces. Select multiple Source Faces to create an average Source Face result. Combine different people to create a blend, or select the same person from different Source Faces to improve the likeness of the person
* Source Faces Shortcuts to always have access to your favorite faces. Works with Merged Source Faces too!
* Improvements to layout for workflow efficiency
* Improvements to Target/Source Face selection for workflow efficiency
* Mousescroll on Target/Source Faces and Target Videos
* Much lower memory requirements (only 2.7GB if you don't enable GFPGAN, CLIP, etc.)
* Mouse scrolling in the video player cycles through the Source Faces for the selected Target Face. Quickly view your Source Faces against the Target Face!
* More speed improvements. Results below. I'll start tracking benchmarks for each release
* (experimental) Mouth parser. Another occlusion tool just for the mouth area. Improves dialogue and lip sync, but will replace the Source Face mouth.
* Bug fixes

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


