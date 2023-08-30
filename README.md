# FishSenseLiteGUI
Image Viewer allowing users to draw bounding boxes around specific features of interest in an image. This was intended to work solely for fish features (head, tail, body), but there is no specific reason it has to be restricted to fish alone.

## Image Loading
Upon opening the app, the user will be asked to choose a directory with the images they wish to use. As of now, the user is unable to choose multiple directories, or individual images - they must choose the entire directory. Nevertheless, the user can return to the first page and choose a new directory whenever they want.

After choosing the new directory, the program will automatically create a SQLite database (if a properly named DB does not exist already) to store the annotations. The user has the option to delete individual images, solely as a last resort. Generally, it would be best to move the images beforehand using your file explorer, or skip over the images as adding/removing images does not change the way the app works. Please use the toggleable button with caution as you need to reload the entire directory if you accidentally delete the wrong image.

Here, double clicking an image path will display the image automatically on the third page. Now, you're in annotation mode.

## Annotation Mode
| Hotkey |Action|
| ------ | -------------------------------|
|   H    |(H for fish head) Bounding boxes are red |
|   T    |(T for tail head) Bounding boxes are green |
|   B    |(B for fish body) Bounding boxes are blue* |
|   A    | Previous image (WASD) |
|   D    | Next image (WASD) |

* color options are being changed in a future commit
  
Using the above hotkeys, the user can move through the directory's images and draw bounding boxes of different colors. The annotations themselves will be stored in the SQLite database with the image path and the pixel location of the images themselves. After storing the annotations, the user will be able to return to the image later on and find the same annotations they or another user drew. 

## Future Todos:
* Add user metadata to the database (username, OS, timestamp, etc.)
* Add automatic laser detection and confirmation options
* Add automatic fish segmentation and confirmation options
