# Usage

The usage guide for created models.

## Getting the Model

Every 3D model, including its textures and other supporting resources, is stored in a *feature branch* in the git repository. The feature branches follow a naming scheme, so you can easily identify the correct branch:

```
<game>-<unit_id>-<unit_name>-<optional>
```

`<game>` is the game the model appears in, `<unit_id>` is the internal unit id from the `.dat` file, `<unit_name>` is the human-readable name of the unit and `<optional>` an optional string to further differentiate units. If you want to find the branch of the Archer model for Age of Empires 2, you therefore have to select the branch named `aoc-4-archer`. The meso-american barracks from Age of Empires 2 can be accessed in the branch `aoc-12-barracks-meso-feudal`.

A full list of game tags, unit IDs and unit names can be found [here](id_reference/game_tags.md).

Select the branch and download it by pressing the green "Clone or download" on Github's interface.

## Creating a Spritesheet

openage cannot directly use 3D models, so you have exact still frames from the model to create a *spritesheet*. We provide sprite generation scripts in the [openage-modding repository](https://github.com/SFTtech/openage-modding/tree/master/scripts/blender).

## Submitting Changes or Features

If you add a feature (like a texture or an animation that was missing before), you can resubmit the model to this repository to make the changes "official". Read the [submission guide](submitting.md) for more information.
