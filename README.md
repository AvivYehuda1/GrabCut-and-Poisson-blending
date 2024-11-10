# **GrabCut and Poisson Blending**

This project implements the **GrabCut** algorithm for foreground segmentation and utilizes **Poisson Blending** for seamless background replacement. These techniques are fundamental in image processing for tasks such as object extraction and image compositing.

## **Features**

- **Foreground Segmentation**: Accurately extracts foreground objects using the GrabCut algorithm.
- **Seamless Blending**: Integrates extracted objects into new backgrounds with Poisson Blending to ensure natural transitions.
- **Manual Initialization**: Allows users to define initial bounding boxes for segmentation.
- **Python Implementation**: Provides a clear and accessible codebase for educational purposes.

## **Project Structure**

- `grabcut.py`: Implements the GrabCut algorithm for foreground segmentation.
- `poisson_blending.py`: Contains the Poisson Blending algorithm for seamless image compositing.
- `data/`: Directory containing sample images and masks for testing.
- `README.md`: Project documentation.

## **Usage**

1. **Foreground Segmentation with GrabCut**:

   Run the `grabcut.py` script with the path to the input image and initial bounding box coordinates:

   ```bash
   python grabcut.py --input_path data/input.jpg --rect 50,50,150,150
   ```

   - `--input_path`: Path to the input image.
   - `--rect`: Initial bounding box coordinates in the format `x,y,width,height`.

2. **Seamless Blending with Poisson Blending**:

   After extracting the foreground, use the `poisson_blending.py` script to blend it into a new background:

   ```bash
   python poisson_blending.py --src_path data/foreground.png --dst_path data/background.jpg --mask_path data/mask.png --output_path data/result.jpg
   ```

   - `--src_path`: Path to the extracted foreground image.
   - `--dst_path`: Path to the background image.
   - `--mask_path`: Path to the mask image.
   - `--output_path`: Path to save the blended result.

## **Examples**

Sample images and masks are provided in the `data/` directory. To test the full pipeline:

1. Extract the foreground:

   ```bash
   python grabcut.py --input_path data/input.jpg --rect 50,50,150,150
   ```

2. Blend the extracted foreground into a new background:

   ```bash
   python poisson_blending.py --src_path data/foreground.png --dst_path data/background.jpg --mask_path data/mask.png --output_path data/result.jpg
   ```

The resulting image will be saved as `result.jpg` in the `data/` directory.

