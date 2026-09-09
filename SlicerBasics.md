# Slicer Basics!

## Pre-workshop

Everyone should have Slicer and SlicerMorph installed using the pre-workshop instructions. If you haven't done that, the instructions are [here](https://github.com/scutisorex/SlicerWorkshop-04-2025/blob/main/pretraining-setup.md).

## Slicer UI and file types

### Default settings

- You can set up Slicer to have useful defaults. SlicerMorph has [a tutorial](https://github.com/SlicerMorph/Tutorials/tree/main/MorphPrefs) on how to set up useful defaults for geometric morphometrics - try setting those up for yourself, and mess around with the defaults if you like! You will probably want to revisit this once you've developed your Slicer workflow, because everyone relies on specific modules, and you can customize your shortcut buttons to make your work easier.

- While you're in preferences, switch volume rendering to be done with GPU ray casting - it's more efficient. MAC USERS NOTE: if you are on Mac, nothing that you load can be larger than 2048px in ANY dimension if you use GPU ray casting.

- You can also switch to dark mode in preferences. 10/10 would recommend to reduce eye discomfort!

### UI info

- Open Slicer and take a look at the various windows and buttons. There are a lot of them and it's not immediately clear what they do. Don't worry, we're gonna interact with most of them, which will help you figure out and remember what they do. To help you get started, [here's](https://slicer.readthedocs.io/en/latest/user_guide/user_interface.html) an overview of the Slicer UI. Check that out.

To get started:

- Toolbar: where all the buttons are to get to where you want to be - i.e., switch modules. You can customize what modules have quick access buttons in the toolbar.

- Module search function: Click the magnifying glass next to the word "Modules" in the toolbar, and start typing the name of your module. This will save you a lot of scrolling!

- Forward, backward, and recent module buttons: To the right of the dropdown showing the current module, there is a button with a black-to-white gradient on it, then arrows pointing left and right. Clicking the gradient button will show you the list of recently used modules. The right and left arrow buttons work like browser forward and back buttons (respectively) for your recently used modules. You can also hit **CTRL+F** and it will open the Module Finder. 

Next, navigate to the Sample Data module and open one of the sample data sets. Scroll through the slices and look at the type of things you can see. The three orthogonal slices and one 3D view is pretty typical of software that has volume-data segmentation capabilities. Use the sample dataset you opened to explore more of the options in the [UI interface overview](https://slicer.readthedocs.io/en/latest/user_guide/user_interface.html).


### Data hierarchy and file saving

- **How are data organized in slicer?** You can see everything in your scene using the Data module. It's a nested hierarchy of what they call "nodes". Right now we've only got the data that loaded from the Sample Data module, but it's easy to add more data. If you right click on a thing in your data module, there will often be a list of actions you can take relating to that data set. Try this whenever we load or create a new node!

- **What happens when you click Save?** It brings up a dialog box with everything that you have in the scene. Note that you need to specify the location where you want to save EVERY item! (note the "Change directory for selected files" option, you will want that, I promise)
- The overall scene file, which ends in .mrml, preserves everything just as you have it when you save. HOWEVER: it does this by referring to the files individually, in the locations where you save them. This means if you move a thing that is referred to in the scene, the scene will not be able to find it and will give you an error when trying to reopen.
- If you just need to save one or two things, you can also right-click on them in the Data module and choose "Export to file...".
- For more info on data and saving in Slicer, refer to [this documentation](https://slicer.readthedocs.io/en/latest/user_guide/data_loading_and_saving.html).

## Data Import

As we discussed in the introductory presentation and chat, there are a couple data types you might want to use. 

**First, let's look at CT/volume data.** There are two main file types you're gonna run into:
- DICOM stacks. These are commonly used in medical imaging, so if you get data from a medical scanner (if you stick a whole mummy in there or whatever), it might be this format. Work through [this tutorial](https://github.com/SlicerMorph/Spr_2021/blob/main/Day_1/DICOM/DICOM.md) on how to import a DICOM stack. It uses a dataset from MorphoSource [(ouvc:10681 Chelydra serpentina)](https://www.morphosource.org/concern/biological_specimens/000S22699), which you can grab [here](https://www.dropbox.com/scl/fi/yubzxyq4iqlrzswn3xdeo/morphosource_media-2024-07-08-09_59_09.zip?rlkey=wtucatvaechj6miiukyllro0k&st=lcvdeflf&dl=0).
    - **PSA!** If you use MorphoSource specimens for any of your research, make sure you [cite  the data you use!!!](https://www.morphosource.org/assets/ms_usage_std_comm_no_rearc_any_3d_limited-6825f6b0844a909f36f31f4b49aacf473a24694ff229c55b19c1cb5b2fe60f01.pdf) It helps not just MorphoSource, but also the collection that the data came from, and the person who originally collected the data. You agree to do this when you download MorphoSource data. As a MorphoSource contributor, I have seen presentations at scientific meetings that use, with zero attribution, scans that I uploaded, and it drives me insane. It's freely available, high-quality morphological data. The least you can do is say where you got it. Don't be that guy.
	
- Image stacks (e.g., .tif files), often the output of a µCT scanner. These come as stacks of 
image files that are numbered and go together to form a 3D volume. There are a couple ways to import this type of data into Slicer, and both have advantages and disadvantages.
	- First: Get yourself a little data set from [here](https://www.dropbox.com/scl/fo/zrntxx7xvvdcnqigjri3x/AMyXGZHCDZa29_EKANAG_oc?rlkey=v05k3xily6tud1ax4vjwn9j35&st=dzsnecye&dl=0). Any of the .zip files are good except for the MorphoSource one we used above, which is only DICOM. You get to pick from among 2 species of mole, one moonrat, and one shrew, but you have to figure out which is which! :) Note that each specimen has a ScanSettings document with the scan resolution - you will need that for import.
	- **Load option 1:** use the basic data loader by clicking on the little file folder in the upper left of the screen. Then you can click "add directory" and choose the folder with your image stack in it. Then it will automatically load in your data. HOWEVER, a common problem with this method is that it will sometimes incorrectly assume the spacing of your slices. If this happens, you have to [update your slice spacing with the Volumes module](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumes.html#load-a-series-of-png-jpeg-or-tiff-images-as-volume).
		- **N.B.:** "Volumes" and "Volume rendering" are two different modules that do different things. Here we are using "Volumes".
	- **Load option 2:** Use the ImageStacks module through SlicerMorph. Work through [this tutorial](https://github.com/SlicerMorph/Tutorials/tree/main/ImageStacks) on how to import image stack data using the module. You can use the same data set as you used for option 1, or you can use the skull from the tutorial. The eagle-eyed among you may have noticed that [the official Slicer Volumes documentation](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumes.html#load-a-series-of-png-jpeg-or-tiff-images-as-volume) now recommends this option. It's better if you have a big data set or only want to work on part of the data - it allows you to load the data at lower resolution, select the part you want to work on, and then load *only that part* at full resolution. I use this method for data loading almost exclusively.
		- For this tutorial - there is a part that says to use the "Annotation ROI", but the Annotations module is deprecated (no longer exists in the current version of Slicer). You will need to [make a new ROI using the Markups module.](https://slicer.readthedocs.io/en/latest/user_guide/modules/markups.html)

**For surface models**, all you have to do to import them is drag them from the folder they are in and drop them onto the scene. Try it with [this lovely model](https://www.dropbox.com/scl/fi/i61e6mmm0ib5mp8r0vmql/FMNH_158008_Crocidura_nana_L03of6_noTB.stl?rlkey=xribysym1nr6jz86sgzrx7kdx&st=xjmbaksu&dl=0) (yes of course it's a shrew vertebra, trying to stay on brand over here). This should work with most kinds of 3D mesh files. 

Now that you have your bearings in the UI, let's do some [fun stuff with modules!](https://github.com/scutisorex/SlicerWorkshop-04-2025/blob/main/SlicerVisAndSeg.md)