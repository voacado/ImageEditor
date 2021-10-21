# Running the program

To run the program, use either the .jar file or MainRunner class in the project (located at /src).

To run the MainRunner, import the project into InteliJ and run the main class.

To run the .jar file, open a terminal shell in the same directory as the .jar file (located at /res) and type:
java -jar "Assignment 6.jar" (arguments).

The following arguments are available:

| Argument           | Purpose                                                   |
|--------------------|-----------------------------------------------------------|
| -script (filePath) | Load a script and terminate once the script has ended.    |
| -text              | Start the program in a textual (command-line based) view. |
| -interactive       | Start the program in an interactive (GUI based) view.     |

# Interactive View:

This is the default view of the program:

[![Default-View.png](https://i.postimg.cc/7LJv8nV4/Default-View.png)](https://postimg.cc/KKbptLwp)

The software is split into various sections.

In the top-left, the user has access to image manipulation operations such as Blur, Sharpen, Grayscale, Sepia, Mosaic, and Downscale.  
In the bottom-left, the user can generate a patterned-image.  
On the right-side, the user can view the layers they have and modify them with the buttons at the bottom right.  
In addition, there are menu items at the top which mimick the buttons shown in the GUI as well as options to save and load files.

## Interactive View: The Process

1. Intially, the user will want to create a layer. Enter a layer name into the text box at the bottom-right. Then hit the "Add Layer" button.
2. The user needs to select a layer to be active. Select the layer from the layer list on the right, then click on the "Set Current Layer" button.
3. Now, the user can load an image into the layer. They can do this by either:
   1. Generating an image using the tool at the bottom-left titled "Generate Image".
   2. Loading a file from the File menu at the top-left through "Load into Layer" (load an image file), "Load All" (load a stacked ppm file), or "Load Script" (load a script-based text version of the program).
4. Once an image is displayed on the center screen, the user can now modify the existing image with operations or layer visiblity, or create new layers.
5. Once the user is content, they can export the image from the File menu with "Save" (save the top-most visible layer) or "Save All" (save all the layers into a stacked ppm file).

## Interactive View: Layer Menu

In the layer view, a layer is the current layer if it is bolded and hidden if it is italicized (as well as have "Hidden" appended to the layer name). 

[![image.png](https://i.postimg.cc/T1wqFCVq/image.png)](https://postimg.cc/ygMZShrk)

The textbox is purely used for adding a layer as it will be the field for layer names. On the other hand, the other buttons (Remove Layer, Toggle Layer Visiblity, and Set Current Layer) will require the user to select a layer from the layer list on the right.

## Interactive View: Other User Inputs

By default, any text box that requires user input (besides the layer name text box) will require a whole number (integer). The exception is downscaling, where the program will want a decimal number between 0.0 to 1.0.

The user also has the ability to undo actions using the "Undo layer" option found under the Edit menu. This option undos an operation on a layer-by-layer basis, keeping a history for each layer individually.




# Textual View: Available Script Commands

The following formats are supported:

imageType = .ppm, .png, .jpg, (layered - using "all" commands)

patternType = checkerboard


Before making a layer, a user has access to the following commands:

| Command                   | Purpose                                                                                                            |
|---------------------------|--------------------------------------------------------------------------------------------------------------------|
| quit                    | Exits the software.                                                                                                |
| createLayer (layerName) | Creates a layer named (layerName).                                                                                 |
| loadScript (filePath)   | Load a script at (filePath) from content root directory.  The script is a list of commands like a user would make. |
| loadAll (filePath)      | Load a layeredImage (.txt file created by our model) at (filePath).                                                |


After making a layer, before selecting a current layer, the user has access to the following commands:

| Command                     | Purpose                                                                                                                      |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------|
| current (layerName)         | Sets (layerName) to the current layer, where the current layer receives any operations and filters called.                   |
| remove (layerName)          | Removes (layerName) from the existing list of layers.                                                                        |
| invisible (layerName)       | Sets (layerName) to be invisible, which means it will not appear when saved or exported to the content root.                 |
| visible (layerName)         | Sets (layerName) to be visible, which means it will appear when saved or exported to the content root.                       |
| saveAll (fileName)          | Save all layers in the current layered model into a single .txt file at (fileName) that can later be imported using loadAll. |
| save (fileName) (imageType) | Save the top-most visible layer to (fileName) in the file format (imageType).                                                |


Once an empty layer is selected, the user has access to the following commands:

| Command                                                | Purpose                                                                                                                |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| load (filePath) (imageType)                            | Load an image from (filePath) that is of type (imageType). This image will become the image of the current layer.      |
| generate (patternType) (width)  (height) (patternSize) | Create an image pattern of (patternType), where the image has (width) and (height) dimensions with (patternSize) size. |


Finally, once a non-empty layer is selected, the user has access to the following commands:

| Command   | Purpose                                                |
|-----------|--------------------------------------------------------|
| undo      | Undoes the last operation on the current layer.        |
| blur      | Blur the image in the current layer.                   |
| sharpen   | Sharpen the image in the current layer.                |
| grayscale | Convert the image in the current layer into grayscale. |
| sepia     | Convert the image in the current layer into sepia.     |

# Layer Status

As long as there is a non-empty layer in the instance of the software, the software will print out information about the current status of the layers, the current layer selected, and the amount to max amount of layers.

Example:  
Layers: 1 / 20  
Current Layer: l1  
Layers:  
1- l1

where the following is represented as:

Example:  
Layers: (current amount of layers) / (maximum amount of layers)  
Current Layer: (name of current layer)  
Layers:  
1- (name of first layer)  


