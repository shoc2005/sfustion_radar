# Radar - final project

## 2D CFAR algorithm description

A constant false alarm rate (CFAR) estimation algorithm was implemented for the 2D case.
 
The function 'subarea' creates a sliding window (a sub-area of a 2D matrix) for the current position in the matrix.
The algorithm uses a loop (looping by rows and by columns of the matrix) which moves a sliding window within all elements of the matrix. Each position of the window represents an average value for training cells (that is implemented by applying a subtraction of the guard cells' sum value from the training cells' sum value and finally obtaining an average value under the sliding window). Next, the average value is used to determine a threshold value finally used in filtering of FFT values.

## Selection of Training, Guard and offset
Within some number of experiments were concluded that an offset of threshold value is best in range 1.3-1.5 due to maximal value after FFT is 45.0762. In the same time a number of Training and Guard cell used as small as possible to optimize performance of CFAR. Good results were obtained by Tr_num=2 an Guard_num = 2. This was possible due to samples of data contain relatively homogeneous level of the noise.

The non-thresholded cells were managed by the implementation of the CFAR 2D algorithm. If the sliding window is outside the matrix missing elements were not used!
