# Tabletop simulator config

https://steamcommunity.com/sharedfiles/filedetails/?id=3183990435

For the workshop to work seamlessly we need to do a couple of things.

1. In freecad:
    1. Make sure all the hex pieces are transformed to be in the origin and rotated in the right direction.
    1. Export them as STLs to the HDD.
    1. Delete the original meshes and import back the STLs previously created.
        - This is done so that the meshes in freecad have the correct positioning baked into the imported STL, instead of transformation values
        - IF this workaround is not done, then scaling the STLs to be smaller would reset the transformations and have the meshes be in their original positiona and orientation.
    1. Scale the Meshes to the appropriate sizes.
        1. Board needs to be at 0.1 scale
        1. Hex pieces need to be at 0.095 scale
    1. Export all meshes as STL
    1. Each STL needs to be improted to Blender and exported as Wavefront (.obj) files.
    1. The board STL needs to be also decimated at a 0.15 rate to reduce the face count, allowing for it to be loaded to TTS.
    1. Create a new workshop and setup go to Options > Grid.
    1. Set up a grid with Vertical Hexes, showing the lines, stapping at center and set the size in both X and Y to 3.87
        - This grid size matches the one in the board model.
        - The appropriate size was determined by loading a model with only the "lines" between the hex slots on the board and matching the lines of the grid with that of the test model.
    1. Load the board as a custom model.
        1. Load the board Wavefront (.obj) file as the model and as the collider.
        1. Defined the model as Non-convex
        1. Define the type as Board.
        1. Rotate and move to center of grid.
        1. Lock the object.
    1. Load on Hex piece and clone it until all of the places in the board are filled.
        - There should be no problem with the borders of the board and the slots, as we calculated the grid size apropriatly.
    1. Create snap points on each of the loaded models
    1. Remove the hexes (leave 1 for testing)
    1. Deactivate the grid (Reset)
    1. Test the positions of the hexes with one Hex in al positions.
    1. Save/update the workshop