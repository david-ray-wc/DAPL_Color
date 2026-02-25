# DAPL_Color DCTLs

DAPL_Color is a suite of DCTL color tools for color grading and look development. The tools prioritize the gentlest operations possible with a "net zero" philosophy. The tools can be used piecemeal for subtle changes, or combined for strong macro-level looks.

## Net Zero Philosophy

The tools use simple operations across 2 color models: 3x3 Matrix, and Tetrahedral.

### Separation/Saturation

Adds to the color's main channel and subtracts an equal amount from the secondaries.

**Example #1**

3x3 Matrix: DAPL_Separation or DAPL_Matrix

- \+8 to Red's R Channel
- \-4 to Red's G Chanel
- \-4 to Red's B Channel

**Example #2**

Tetrahedral: DAPL_Saturation or DAPL_Tetra

- \+6 to Magenta's Red Channel
- \-12 to Magenta's Green Channel
- \+6 to Magenta's Blue Channel

### Crosstalk/Hue

Adds and subtracts equal amounts between secondaries without touching the main channel.

**Example #1**

3x3 Matrix: DAPL_Crosstalk or DAPL_Matrix

- \+0 to Red's Red Channel
- \+4 to Red's Green Channel
- \-4 to Red's Blue Channel

**Example #2**

Tetrahedral: DAPL_Hue or DAPL_Tetra

- \+8 to Magenta's Red Channel
- \+0 to Magenta's Green Channel
- \-8 to Magenta's Blue Channel

## Usage

Any of the tools can be used separately or in conjunction with each other. It's generally easier to place the matrix nodes before the tetra nodes. Event though they're meant for log footage, they are gentle 3D transformations that could even be applied to Rec709 8 bit footage.

One of the inspirations for this project is Baselight's Chromogen, which is a simple set of operations serially stacked across a custom color model. This is much more simple and doesn't claim to match any chromogen results, but it is free.

The DAPL_Crosstalk, DAPL_Separation, DAPL_Hue, and DAPL_Saturation tools are meant to be used in this way.

## Recipes

Another inspiration is the "recipe" culture that Fujifilm has with their mirrorless cameras. The DAPL_Matrix and DAPL_Tetra tools are integer sliders in order to facilitate the creation and sharing of recipes. View them on the [Recipes Page](Recipes.md).

## Limitations

The current toolset is limited to 3D hue transformations and never touches the neutral axis. It is not able to create contrast or split toning, which are other core elements of look design and show LUT creation.
