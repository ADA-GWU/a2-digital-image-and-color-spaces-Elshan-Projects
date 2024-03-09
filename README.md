_The captured images are stored in the "Original Images" folder (image_1.jpg, image_2.jpg, image_3.jpg)._

# 1. Grey Scale Conversion
+ The resulting images are located in the "Grey Scale Images" folder which contains a subfolder for each test image.
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
+
