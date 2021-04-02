# Reproduce the matlab ssim in pytorch


SSIM are **not** consistent in several implementations. For example, skimage calculate the average of the SSIM of the individual channels, while matlab adopts a 3D gaussian kernel. The inconsistence can be found here https://github.com/scikit-image/scikit-image/issues/4985 . 
Some communities, such as low-level vison community, tend to report the ssim provided by matlab in the paper. However, I did not find such a reproduce (they failed to reproduce the result with a difference < 0.0001) in the python community, so I created one.

#### usage
python calc_ssim.py

#### result
It should print a number ~ 0.8434 (The result of matlab is 0.8433).
The difference (0.0001) might be a numerical problem caused by the difference between pytorch and matlab implementation.
