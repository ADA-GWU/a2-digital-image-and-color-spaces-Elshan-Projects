_The captured images are stored in the "Original Images" folder (image_1.jpg, image_2.jpg, image_3.jpg)._

# 1. Grey Scale Conversion
+ The resulting conversion images are located in the "Grey Scale Images" folder which contains a separate subfolder for each test image.
### Qualitative Analysis
+ The NTSC greyscale conversion showed better outcomes in capturing shadows and semi-shadows for Images 1 and 2, whereas the 1/3 weights conversion method was better at distinguishing between darker color hues under the belly of the dog in Image 1 and around the ears in Image 2.
+ For Image 3, the nearly identical resulting images for both conversion methods are due to the image's uniform lighting and contrasting colors of the carpet.
### Quantitative Analysis
When comparing the greyscale conversions of three images using both the NTSC and 1/3 weight methods, the Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index (SSIM) were used as metrics.
+ Image 1: The NTSC method yields a significantly higher PSNR of 77.99 compared to 27.05 for the 1/3 weights method, suggesting that the NTSC conversion retains a much closer match to the original image in terms of signal accuracy. Similarly, the SSIM is perfect (1.0000) for NTSC, indicating an exact match, while the 1/3 weights method scores slightly lower at 0.9872, implying a very high but not perfect structural similarity.
+ Image 2: Similar to Image 1, the NTSC method outperforms the 1/3 weights method with a higher PSNR (79.99 vs. 36.17) and a perfect SSIM score (1.0000) compared to a slightly lower SSIM (0.9902) for the 1/3 weights. This suggests that, as with Image 1, the NTSC conversion maintains a closer fidelity to the original image's detail and structure.
+ Image 3: The NTSC method shows a higher PSNR (85.40) than the 1/3 weights method (40.69), with both methods achieving very high to perfect SSIM scores (1.0000 for NTSC and 0.9985 for 1/3 weights). The quantitative metrics suggest excellent performance by both methods, with NTSC having a slight edge in signal accuracy.
### Instructions
+ The script name _Grey_Scale_Elshan_Naghizade.py_
+ Dependencies: Pillow, matplotlib, numpy, scikit-image (Use __pip install _package name___ to install)
+ Driver Function: grey_scale_driver("IMAGE_PATH")
+ Run the script and then call the driver function with the image path as its parameter
+ The driver function will display the original image along with the NTSC and 1/3 conversion results and then save the resulting images in the same folder that contains the script.
### Code Overview
+ convert_to_ntsc_greyscale(image): Converts an RGB image to greyscale using NTSC coefficients (0.2989 for Red, 0.5870 for Green, and 0.1140 for Blue), which are intended to reflect the human eye's sensitivity to these colors.
+ convert_to_one_third_greyscale(image): Converts an RGB image to greyscale by averaging the three color channels (Red, Green, Blue) equally, giving each one-third weight.
+ calculate_metrics(original_image, converted_image): Calculates and returns the Peak Signal-to-Noise Ratio (PSNR) and the Structural Similarity Index (SSIM) between the original image and a converted greyscale image. These metrics assess the quality of the conversion in terms of signal accuracy and perceived visual similarity, respectively.
+ save_and_show_images(original_image, ntsc_grey_image, one_third_grey_image, original_path): Saves the greyscale images (converted through both methods) with specific filenames indicating the conversion method. Then, it displays the original image alongside the two greyscale versions in a single figure for visual comparison.
+ grey_scale_driver(image_path): Acts as the driver function for the entire script. It opens the specified image file, performs both greyscale conversions, calculates PSNR and SSIM for each conversion method, prints these metrics, and invokes save_and_show_images to save and display the results.

# 2. Color Quantization
+ The quantizations of the images are stored in the "Color Quantization Images" folder with a separate subfolder for each test image. Consequently every test image's subfolder contains 2 subfolders (Uniform and K-means Quantization). Those subfolders contain the quantizations with the following bucket sizes (2,4,8,12,16,32,64,128) for their respective quantization algorithm
### Instructions
+ The script name _Color_Quantization_Elshan_Naghizade.py_
+ Dependencies: numpy pillow matplotlib scikit-learn (Use __pip install _package name___ to install)
+ Driver Function: _quantization_driver('image path', n_buckets_list)_
+ Run the script and then call the driver function with the image path and n_buckets_list as its parameters
+ _n_bucket_list_ is a list containing integer values denoting the buckets for which the Uniform and K-Means quantization will be performed
+ The driver function will display the original image along with the resulting images for every bucket number for both algorithms and then save them under the following naming convention: __name of the file + the algorithm + bucket size__
### Code Overview
+





