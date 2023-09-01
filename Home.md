# Overview
![image](https://github.com/Hillobar/Rope/assets/63615199/598f02c9-3680-4717-af2e-0ed2256ebd47)

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

### Occluder
<img src="(https://github.com/Hillobar/Rope/assets/63615199/fd4a0d96-f3f7-4e9d-8407-c8c20d80f5a2" width="150">

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
