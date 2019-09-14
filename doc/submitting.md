# Submitting

The submission guide for replacement models for AoE1, AoE2, SWGB and the Definitive Editions.

## Software

**3D Assets**

* [Blender](https://www.blender.org/) (version >= 2.8): 3D modeling, animating and rendering

Using Blender is required. We currently do no accept other formats.

**2D Assets**

Recommended:

* [Krita](https://krita.org/): great out-of-the-box image manipulation and drawing tool
* [GIMP](https://www.gimp.org/): swiss army knife of image editing with loads of plugins and extensions available

Photoshop, Corel, Affinity Photo or Paint.NET are also allowed, although we prefer open formats as well as software that work on GNU/Linux and BSD.

## Quick Start Guide

If you know [git](https://git-scm.com/book/):

1. Fork the repo
2. Check out the branch of the model you want to work on
3. Create your model
4. Commit your creation and make a pull request
5. Wait for our review
6. Rejoice!

If you don't know [git](https://git-scm.com/book/):

1. Create your model
2. Make a Github account (if you don't have one)
3. Create an [issue](https://github.com/SFTtech/openage-data-3dmodels/issues) with the name of the unit and the game in the title. Attach the files in a `.zip` file
4. Wait for our review
5. [Learn git](https://git-scm.com/book/)
6. Rejoice!

## Creating the model

### Selecting the branch

Every 3D model, including its textures and other supporting resources, is stored in a *feature branch* in the git repo. The feature branches follow a naming scheme, so you can easily identify the correct branch:

```
<game>-<unit_id>-<unit_name>-<optional>
```

`<game>` is the game the model appears in, `<unit_id>` is the internal unit id from the `.dat` file, `<unit_name>` is the human-readable name of the unit and `<optional>` an optional string to further differentiate units. If you want to find the branch of the Archer model for Age of Empires 2, you therefore have to select the branch named `aoc-4-archer`. The meso-american barracks from Age of Empires 2 can be accessed in the branch `aoc-12-barracks-meso-feudal`.

A full list of game tags, unit IDs and unit names can be found [here](id_reference/game_tags.md).

### Requirements for Models

#### Style

For our replacement graphics, we encourage the "similar but distinct" approach that [OpenTTD](https://www.openttd.org/) used in their project. Their concept is described [here](https://wiki.openttd.org/Graphics_Replacement#Artwork):

> New art is being drawn in the style of the original game, using the original 8bpp palette. The graphics should be a similar but distinct version of the object in question - no graphics [= textures or sprites] may be copied at all from the original. [...] Where possible glitches/bugs in the original graphics should be avoided [...]

In other words, the models should be close to the original, but do not have to be exact copies.

Objects in AoE1 and AoE2 often have a very recognizable shape, size and color. Keep that in mind when you design your model. Textures of buildings should also match the general style of the civilization they are part of. Consistency and recognizability are preferred over historical accuracy.

#### Naming and Structural Conventions

To be compatible with our sprite generation scripts, we require a few (minor) conventions for the `.blend` file.

**Scene**

* Put every mesh object that should be rendered in a Collection with the name `render_me`. This should only contain meshes and not lights, cameras, shadow catchers, etc.
* Let the model face towards the positive x-axis.
* Create a camera `dim_camera_45` with rotation (X=60°, Y=0°, Z=45°) and orthographic type, set it as the active camera and fit it to the model. You can do the latter by selecting everything in `render_me` and the camera, then do
  * View -> Align View -> Align Active Camera to Selected

**Animations**

* Assign an appropriate prefix to the name an **Action** like `move_<something>` or `idle_<something>` (replace `<something>` with a more descriptive string like an index).
* Remove Actions that are not used in NLA tracks or - if you think they are still useful for others - at least mark them as ununsed by prefixing them with `X_`, e.g. `X_move_<something>`.
* Our scripts render the sprite by using NLA tracks. Create at least one NLA track for every animation. The naming convention for the NLA track is
  * `<animation_name>_<index>` in all lowercase and the index starting at 0. Examples: `move_0`, `attack_2`

**Others**

* Please use descriptive names for everything. People who want to build on your work will thank you and the reviewers will be happy, too :) By the way, did you know that you can [add comments in the node editor](http://web.archive.org/web/20190914181655/https://blender.stackexchange.com/questions/7825/is-there-a-way-to-make-comments-in-the-node-editor/32842#32842)?


#### File structure

Your files should be placed a directory in the repository root. Give the directory the name of the branch.

The `.blend` file should be named like the branch but *without* the game tag:

```
<unit_id>_<unit_name>_<optional>.blend
```

Textures go into a subfolder called `textures`. The source files for textures should be placed in another subfolder `textures_source`. If you have anything else (e.g. scripts), put it in a directory called `auxiliary`.

You also have to create a `README.md` file to describe your model. [We have a template for that.](readme_template/template.md)

**Example structure:**

```
aoc-12-barracks-meso-feudal
|--auxiliary
   |--custom_script.py
|--textures
   |--barracks_texture_0.png
   |--barracks_texture_1.png
|--textures_source
   |--barracks_texture_0.krita
   |--barracks_texture_1.krita
|--12-barracks-meso-feudal.blend
|--README.md
```
