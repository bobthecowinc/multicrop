# MultiCrop by Bob The Cow

MultiCrop is the only simple web application that allows users to crop multiple sections of an image, display them on a canvas, and then export those cropped sections as a ZIP file of JPG images. The app supports dragging and dropping images, selecting an image from a list, cropping selected regions, and exporting them as separate cropped images.

## Features

- **Drag and Drop or File Upload**: Upload JPG images either by dragging them into the drop zone or selecting them through the file input.
- **Canvas Drawing**: Select regions on the canvas to crop. The cropping tool allows you to draw rectangular regions on the image displayed on the canvas.
- **Delete Last Crop**: Remove the most recently drawn crop.
- **Export Crops as ZIP**: After cropping the image, export the selected regions as a ZIP file containing the crops as individual JPG images.
- **Image Selection**: Choose from multiple uploaded images for cropping.

## How it Works

### 1. **Image Upload**

Users can upload images in JPG format using two methods:
- **Drag-and-Drop**: Drag an image into the designated drop zone.
- **File Selection**: Click the drop zone to open a file picker, then select images.

Once an image is uploaded, it is displayed in a list for selection.

### 2. **Canvas Display**

The selected image is displayed on a canvas. The canvas is set to half the size of the original image, preserving the aspect ratio.

### 3. **Cropping Regions**

The user can draw rectangular crop regions on the canvas:
- **Mouse Down**: When the user clicks and holds the mouse on the canvas, the starting coordinates (x, y) are recorded.
- **Mouse Up**: Upon releasing the mouse, the crop region is drawn based on the start and end coordinates. The crop region is added to the list of crops.

Each crop is drawn on the canvas as a red rectangle to indicate the selected region.

### 4. **Delete Last Crop**

Users can remove the most recently drawn crop by clicking the "Delete Last Crop" button.

### 5. **Export Crops as ZIP**

When the "Export Crops as ZIP" button is clicked, the selected crop regions are exported as individual JPG images. The crops are stored in a ZIP file, which is then automatically downloaded to the user's computer.

Each crop is exported at a resolution based on the selected crop dimensions, ensuring that the images are saved as JPG files.

## Components

- **HTML Structure**:
  - `<canvas>`: Used to display the selected image and drawn crop regions.
  - `<div class="drop-zone">`: A clickable area for uploading images.
  - `<select id="imageSelector">`: Dropdown list for selecting uploaded images.
  - `<button>`: Buttons for clearing the last crop and exporting crops.

- **JavaScript**:
  - **Image Handling**: Uses the `FileReader` API to load images and the `canvas` element to display them.
  - **Cropping Logic**: Tracks mouse events (`mousedown` and `mouseup`) to define crop regions.
  - **ZIP Export**: Uses the JSZip library to create a ZIP file containing the cropped images, which is then saved using the `FileSaver.js` library.

## Dependencies

This project uses two external JavaScript libraries:
- **JSZip**: To generate ZIP files containing the cropped images. [JSZip Documentation](https://stuk.github.io/jszip/)
- **FileSaver.js**: To trigger the file download of the generated ZIP file. [FileSaver.js Documentation](https://github.com/eligrey/FileSaver.js/)

Both libraries are loaded from a CDN.

## How to Run the Application Locally

1. Download or clone the repository containing the code.
2. Open the `multicrop.html` file in your preferred web browser.
3. Follow the on-screen instructions to upload an image and start cropping.

## License

This project is open source and free to use. Feel free to contribute or modify the code to suit your needs.

---

If you have any questions, contact [multicrop@bobthecow.org](mailto:multicrop@bobthecow.org)
