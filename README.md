# QRcode-detection-and-recognition

QR code detection and decoding by using python language but no image processing packages (opencv etc).

## Image processing procedure & algorithm:
1. read the input image, convert RGB data to greyscale and stretch the values to lie between 0 and 255;
2. compute horizontal edges
3. compute vertical edges;
4. compute edge (gradient) magnitude;
5. smooth over the edge magnitude (mean or Gaussian, I use mean here), and stretch contrast to 0 and 255;
6. perform a thresholding operation to get the edge regions as a binary image;
7. perform a morphological closing operation to fill holes (dilation and erotion);
8. perform a connected component analysis to find the largest connected object;
9. Extract the bounding box around this region, by looping over the image and looking for the minimum and maximum x and y coordinates of foreground pixels (>0);

Each step could be outputted into the '/images/output_image' folder. Please edit the code if you needed (the relavent code has been well commented at around line 370).

## Things need to be improved:
The bounding box could be changed to polygon based on the shape of the QR code.
The rectangle box would affect the decoded result if the QR code is not perfectly a rectangle.
