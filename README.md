
# Tsallis Entropy-based Image Segmentation

This Jupyter Notebook performs image segmentation using Tsallis entropy. 
Image segmentation is a fundamental task in computer vision and image processing, and Tsallis entropy provides an alternative measure of uncertainty or disorder in an image.

## Requirements

- Python 3.x
- Jupyter Notebook
- OpenCV (cv2)
- NumPy

## Usage

1. Clone the repository or download the Jupyter Notebook file (`tsallis_image_segmentation.ipynb`).
2. Make sure you have the required dependencies installed (`opencv-python`, `numpy`).
3. Open the Jupyter Notebook using Jupyter Notebook app or command line:

jupyter notebook file: tsallis_image_segmentation.ipynb


4. Run the cells in the notebook to perform image segmentation with different threshold and q values.
5. The notebook will display the segmented images for different threshold and q values, along with the Tsallis entropy value for each combination.

## Parameters

- `threshold_values`: List of threshold values to be used for image segmentation.
- `q_values`: List of q values to be used for Tsallis entropy calculation.

## Example


# Evaluate segmentation performance for different threshold and q values
threshold_values = [100, 150, 200]
q_values = [0.7, 0.8, 0.9, 1.0001, 2, 3] # q=1.0001 is for avoiding any division with 0.

for threshold in threshold_values:
    for q in q_values:
        # Segmentation applies.
        segmented_image = segment_image(image, threshold)
        
        # Show segmentation results.
        cv2.imshow(f'Segmented Image (Threshold={threshold}, q={q})', segmented_image)
        cv2.waitKey(0)
        cv2.destroyAllWindows()
        
        # Calculate Tsallis entropy.
        entropy = tsallis_entropy(segmented_image, q)
        print(f'Tsallis Entropy (Threshold={threshold}, q={q}): {entropy}')
        

## References

- [Introduction to Tsallis entropy](https://en.wikipedia.org/wiki/Tsallis_entropy)
- [Documentation for OpenCV Python](https://docs.opencv.org/master/d6/d00/tutorial_py_root.html)
- [NumPy Documentation](https://numpy.org/doc/stable/)
