# Slicer modules: Visualization, segmentation, and exporting meshes

# Overview
There are a LOT of different modules in Slicer that allow you to visualize and manipulate your data. The main things we're going to focus on today are: rendering volumes, transformations, segmenting, and making exportable 3D models of your segmentations. But again - people are doing all sorts of cool stuff with Slicer. Go on Google Scholar and search "3D Slicer" and you will find a huge variety of other tools! You can also search directly in the extension manager.

**HOT TIP!** You can find handy shortcuts in Slicer sometimes by right-clicking in a field, on a button, or in a menu, and seeing what comes up. Can't find how to view or manipulate something? Try a right click! E.g.: Right click in any of the 2D views and pick "Slice intersections" to see all three slice locations shown in every view.

## Visualization basics and useful modules
If you have your own volumetric data, you can try importing it now, in whatever format you have (DICOM or image stack). **Remember!** If your data set is GIANT, you may want to load only a part of it or load it at a decreased resolution for exploration purposes. Refer back to our [Slicer Basics page](https://github.com/scutisorex/SlicerWorkshop-04-2025/blob/main/SlicerBasics.md) as needed.

You can also try importing and working on any of the volume data sets found [here](https://www.dropbox.com/scl/fo/zrntxx7xvvdcnqigjri3x/AMyXGZHCDZa29_EKANAG_oc?rlkey=v05k3xily6tud1ax4vjwn9j35&st=rm9rli4b&dl=0). Open your chosen data set in each one of these modules and see what you can do with it. 

**HOT TIP!** In the upper left corner of every module, you will find a little dropdown that says "Help and Acknowledgement". If you expand that, most of the time you will find a useful link to some kind of documentation for the module - a publication, a github, a tutorial, something. If you get stuck, check for this!

### Modules:

- Volume Rendering: [Here's the official Slicer documentation](https://slicer.readthedocs.io/en/latest/user_guide/modules/volumerendering.html) for the module, and [here's a great tutorial](https://github.com/SlicerMorph/Tutorials/blob/main/Slicer_Modules/Volume_Rendering/README.MD) put together by the SlicerMorph team. These describe the basics of how to view and customize your volume.
- Transforms: [Official Slicer documentation here](https://slicer.readthedocs.io/en/latest/user_guide/modules/transforms.html), SlicerMorph tutorial [here](https://github.com/SlicerMorph/Tutorials/blob/main/Slicer_Modules/Transforms/README.md). It's often useful to be able to reposition your object in the scene. Maybe you want to arrange it so its anatomical axes are aligned with those of the scene, or move it closer to another object, or rotate it relative to a markup of some kind. Whatever! Try making and hardening some transforms.
- [Animation](https://github.com/SlicerMorph/Tutorials/tree/main/Animator): Fundamentals of how to make a little movie of your item.
- [Lights](https://github.com/SlicerMorph/Tutorials/blob/main/Slicer_Modules/Lighting/Lights.md): This is an additional tool to make your volumes look nice. It's in an extension called **Sandbox**. If you don't have it installed, this is a great opportunity to practice installing a new extension!

## Segmentation and related explorations

Now it's time to learn one of the most important functions in Slicer: segmentation. This is where you separate an image into different parts and label them. 

In this case, we will be labeling a 3D volume, which consists of a whole bunch of 2D images. If this is your first time ever segmenting, or if you want more in-depth info or a refresher, check out [the official Slicer segmentation documentation.](https://slicer.readthedocs.io/en/latest/user_guide/image_segmentation.html) It's super informative and clear.

- Before you start segmenting, make sure you have the Sandbox extension installed. This will allow you to use the [Segment Editor Extra Effects](https://github.com/lassoan/SlicerSegmentEditorExtraEffects), which are extremely useful. They are covered in the tutorial below. Also install the [SurfaceWrapSolidify](https://github.com/sebastianandress/Slicer-SurfaceWrapSolidify) extension! 

- There are an absurd number of different ways to approach segmentation, and we can't cover all of them. However, we can get through the basic functions in Slicer using [this excellent tutorial put together by the SlicerMorph team.](https://github.com/SlicerMorph/Tutorials/tree/main/Segmentation) Work through it at your own pace, and try to experiment with as many of the tools as you can. They show their examples with the "MRBrainTumor1" sample data set, but you can test out the segmentation tools on any of the data sets we have looked at so far, or any of the data sets in the Sample Data module. Or, if you have your own data with you, feel free to use that!

- I would also encourage you to take a look at the descriptions of segmentation tools in the official Slicer [Segment Editor documentation](https://slicer.readthedocs.io/en/latest/user_guide/modules/segmenteditor.html).

- **N.B.!!** There is a module called Segment Editor, and another one called Segmentations. Just like the "Volumes" and "Volume Rendering" ones. Why they named them this way I'm not sure. Maybe it's their idea of fun. Anyway - be sure you're looking at the right one when you're doing the segmentation tutorials.

- After you've done some segmentation, try out the [Colorize Volume](https://github.com/SlicerMorph/Tutorials/tree/main/ColorizeVolume) module, which is in the Sandbox extension we installed above. It makes stunning 3D renderings of the volume with color labeled by segment. You're gonna like it, I bet. 

- Obviously making your stuff look pretty is important, but you can also take important measurements on segments. Try out the [Segment Statistics module](https://slicer.readthedocs.io/en/latest/user_guide/modules/segmentstatistics.html) to get some quantitative info about the segmentations you make.

## 3D Mesh tools

Slicer is not incredible as a mesh editor, but you can accomplish some basic stuff that you're likely to need. 

Import the 3D mesh of a shrew vertebra listed above and try out some of the functions in the [Surface Toolbox](https://slicer.readthedocs.io/en/latest/user_guide/modules/surfacetoolbox.html) module. I have found the smoothing and mirroring tools to be especially useful for my work!

ALSO - there are a number of extensions available for doing specific edits to meshes. Try and see if you can find one by going to the Extension Manager and searching "mesh".

## Additional tools

For a whole bunch more resources, check out the [Slicer Resources page!](https://github.com/scutisorex/SlicerWorkshop-04-2025/blob/main/SlicerResources.md)