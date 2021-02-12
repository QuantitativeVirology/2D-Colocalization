# 2D-Colocalization
This is a simple Jupyter notebook that creates a 2D heatmap to show colocalization between two fluorescence images.

## General Info

This script takes two images as input and creates a heatmap which is supposed to highlight the areas in the image where the two channels colocalize. The idea behind the script is to normalize both channels to relative intensities and then compare the pixel values for both channels. For this, the pixel values are interpreted as a vector (int_channel_A, int_int_channel_B). In a classical 2D coordinate system this vector starts at (0,0) and has two properties: Length and Angle. The higher the intensities in the channels,the greater the length of the vector and the closer the angle is to 45° the more similar is the relative brightness in both channels. This tool calculates the heatmap intensity of each pixel by calculating the length of the vector and multiply it by y=1-(|cos(x)-sin(x)|), whereby y = 0 at angles of 0° and 90° and y = 1 at the 45° angle. grafik.png By this multiplication the pixels increase in brightness the more similar their relative intensities in the two channels and are darker the more dissimilar their relative intensities are. This tool is especially designed to show spatial relation between colocalizing pixels. It is of limited use to determine the biological relevance of the colocalization because it highlights areas just based on the similarities of their relative intensities.

## How to use this skript

0) This script was made using anaconda3. You may need to install at least the tifffile library if you already use anaconda3

1) Copy two one channel tiffs in the input folder in the directory of this notebook.

2) Run all the boxes from the skript.

3) Save resulting figure.
