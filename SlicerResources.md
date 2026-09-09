# Expand your Slicer knowledge!

Slicer can do so so much more than what we've covered here! If you google pretty much any 3D task with '3DSlicer' attached to it, there's bound to be something. (And if there isn't, you can ask about it on the [Discourse!](https://discourse.slicer.org/) Here are some additional sundry resources that you can use to grow your skills and improve your scientific workflows.

## General Slicer discussion and tips

- [3DSlicer Official Documentation](https://slicer.readthedocs.io/en/latest/index.html)
- [3DSlicer Wiki](https://www.slicer.org/wiki/Main_Page)
- [Slicer Discourse](https://discourse.slicer.org/)

## General tutorial resources

- [All the SlicerMorph tutorials](https://training.slicer.org/#segmentation-tutorials) in one place!
- [Tutorial Compendium](https://training.slicer.org/#segmentation-tutorials): be aware that some of these are based on older versions of Slicer and therefore might have slight differences compared with more recent versions.  

## Segmentation

- [Segmentation recipes](https://github.com/lassoan/SlicerSegmentationRecipes) by Andras Lasso et al. These are a great place to get ideas for how to tackle your segmentation problems. If you're stuck, go look at some of these, even if they don't seem directly related to your task - you might find a new trick or see a strategy you hadn't considered.
- Go on YouTube and search for 3DSlicer segmentation tutorials - there are a bunch of them that might give you new tips and tricks! People are pretty good at figuring out how to make tasks efficient. (i.e., laziness in one form can pay off in the long run with increased productivity!)

## Machine learning segmentation

- nnUNet: training image classifiers to automate segmentation. See their [GitHub](https://github.com/MIC-DKFZ/nnUNet) and [Slicer implementation](https://github.com/KitwareMedical/SlicerNNUnet). This requires you to be ok with messing around in Python, but you can get great results if you're willing to put up with that. This is good for repeated segmentation tasks, and seems surprisingly versatile once you have your training data set ready.
- MONAI Label: "An intelligent image labeling and learning tool to quickly annotate new datasets" (verbiage from the MONAI GitHub). Check out their [website](https://monai.io/label.html), [GitHub for the overall project](https://github.com/Project-MONAI/MONAILabel), and [GitHub for the implementation in Slicer](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/slicer).

## Morphological analysis

- SPHARM (SPherical HARMonics) with [SPHARM-PDM](https://www.nitrc.org/projects/spharm-pdm). You can also use a tutorial I made for this, found [here](https://github.com/scutisorex/SPHARMtutorial).
- [Dental Dynamics](https://github.com/jmhuie/SlicerBiomech?tab=readme-ov-file): a module for executing a number of biomechanical analyses on animals that have A Lot Of Teeth. Developed by fellow SlicerMorph enthusiasts K. Cohen, A. Fitzpatrick, and J. Huie. [Read the publication!](https://academic.oup.com/iob/advance-article/doi/10.1093/iob/obae015/7668472)
- [Segment Geometry](https://github.com/jmhuie/SlicerBiomech/tree/main/Docs/SegmentGeometry): A tool for measuring second moment of area in Slicer. Also introduces the SurfaceWrapSolidify module, which you may find useful. [Read the publication!](https://doi.org/10.1093/iob/obac009)

## Python scripting

You can write your own modules in Slicer using Python scripting, if you're into that sort of thing! It's fun and challenging, and if you have the time to do it, it could help you and others with repetitive niche tasks.

Resources:

- [SlicerMorph example scripts](https://github.com/SlicerMorph/Scripts#2-run-an-image-processing-pipeline-on-a-folder-of-volumes)
- [Script repository](https://slicer.readthedocs.io/en/latest/developer_guide/script_repository.html)
- [Items on the Discourse labeled 'python'](https://discourse.slicer.org/tag/python)
- [Slicer Docs Python FAQ](https://slicer.readthedocs.io/en/latest/developer_guide/python_faq.html)