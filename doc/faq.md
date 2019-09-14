# Frequently Asked Questions

## Submitting

### I want to submit a model that is not part of AoE1/AoE2/SWGB. Is that allowed?

Yes, you can choose to submit any model that could be used for sprites and animations in the engine. To do this, simply create an issue in the issue tracker with the `extra` label assigned. Describe your model or upload the `.blend` files directly for discussion. We will then create a feature branch for you where you can commit the model.

### Do I have to use the Blender or are uploads of Maya/Autodesk/3ds Max also allowed?

Unfortunately, we can only accept `.blend` files and no other proprietary formats. This is done to ensure that everyone can access and work with the models for free and on the platform of their choosing. Also, our sprite creation scripts are primarily made for processing Blender files.

Blender can import formats of other programs, so you can try to first export your model to an `.fbx` file, then import it into Blender and save it as a `.blend` file. However, the imported model might need manual tweaks to fulfill our [requirements](submitting.md).

## Usage

### Can I use your 3D models in my own project?

Yes, everything in the repo can be used freely under the conditions of the [CC-BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/) license. The license basically boils down to two major requirements:

* Give credit where credit is due
* Derivatives of the work have to be distributed under CC-BY-SA 4.0 as well

Read the linked info on the license for more information on how to do that.

## Legal

### Is this legal?

Yes.

### Someone uploaded a model/texture I made without my permission.

In this case, you can create an issue in the public [issue tracker](https://github.com/SFTtech/openage-data-3dmodels/issues) or write us a mail at `copyright ät sft dawt mx`. Please provide the following information:

* Which models/textures are affected?
* Some evidence that you are the creator of the model/texture.
* *Optional*: What we should do with the content you created. By default, we will delete it from the repo, but you can also choose to just add yourself as the author.
