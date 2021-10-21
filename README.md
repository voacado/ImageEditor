# ImageEditor
*(Note: Code available upon request)*

An image manipulation software that can read, generate, and edit commonly supported image formats

## Screenshots
Default Software View:

[![Default-View.png](https://i.postimg.cc/7LJv8nV4/Default-View.png)](https://postimg.cc/KKbptLwp)

*(More screenshots available in Screenshots.md)*

## Functions
- Create and hide image layers
- Export and Load images (png, jpg, ppm)
- Save multiple layers together (ppm)
- Undo Previous Actions
- Image Transformation (Blur, Sharpen, Mosaic, Downscale)
- Color Transformation (Grayscale, Sepia)
- Generate Image Patterns (Checkerboard)

## Purpose
The objective of this program is to act as an image manipulation software. It has the ability to read commonly supported image formats (such as .png and .jpg) and edit these images (such as blur). It can also generate an image based on a pattern (such as a checkerboard). The software also supports the use of layers, allowing for multiple images to be layered on-top of each other and the ability to hide and show specific layers. The software also supports the ability to save and load multiple images from its current state to be restored later.

## Programming Concepts
The software was created in Java using the Model-View-Controller software design pattern which divides the program into three abstracted components, a model that handles the software logic, a view that handles displaying information to the user, and a controller that handles user input.

Each component interacts to each other using the Publisher-Subscriber design pattern which abstracts (using interfaces) the amount of information that each part of the program can interact with, limiting the scope of each component. For example, the View of the program only needs to see what to display in the image viewer and thus, is a subscriber to an ImageProcessingModel subscriber (which handles storing and manipulating images).

The view was created using the Java Swing package with the Flatlaf Look and Feel design.

In order to ensure that the program functioned properly, we tested the software using JUnit4 against various possible scenarios for each function of the program (such as if the math on the blur was applied properly, etc).
