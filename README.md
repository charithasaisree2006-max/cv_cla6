# AIM

To demonstrate **intensity level slicing** of an image by selecting and highlighting pixels within a specified range of intensity values.

# SOFTWARE USED

* **Google Colab**
* **Python**
* **OpenCV (`cv2`)**
* **NumPy**
* **Pandas**
* **Matplotlib**

# THEORY

## INTENSITY LEVEL SLICING

Intensity level slicing is an image processing technique used to **highlight a specific range of intensity values** in an image.

In this technique, a particular range of pixel intensity values is selected and highlighted, while the remaining pixels are either retained or suppressed.

For an 8-bit grayscale image, pixel intensity values generally range from **0 to 255**.

In this experiment, the selected intensity range is:

```text
rmin = 100
rmax = 200
```

Therefore, pixels whose intensity values lie between **100 and 200** are selected.

## WORKING OF INTENSITY LEVEL SLICING

* The input image is loaded using OpenCV.
* The image pixels are examined individually.
* A minimum intensity value `rmin = 100` and maximum intensity value `rmax = 200` are defined.
* The intensity of each pixel is checked.
* If the pixel intensity lies between 100 and 200, it is considered part of the selected range.
* The selected pixels are highlighted with a value of **255**.
* Two different results are generated:

  * **Slicing With Background**
  * **Slicing Without Background**
* The processed images are displayed using Matplotlib.

## INTENSITY RANGE USED

The intensity range used in this experiment is:

```text
100 ≤ intensity ≤ 200
```

Pixels satisfying this condition are highlighted.

Pixels outside this range are treated as background depending on the type of slicing being performed.

## SLICING WITH BACKGROUND

In **slicing with background**, the selected intensity range is highlighted while the original background information is retained.

The selected pixels are assigned a value of **255**, making them appear bright in the output image.

This method allows both the highlighted region and background information to be observed.

## SLICING WITHOUT BACKGROUND

In **slicing without background**, the selected intensity range is separated from the background.

The selected pixels are assigned a value of **0**, while pixels outside the selected range are assigned **255** according to the implemented code.

This produces a binary-like representation that helps identify the selected intensity region.

## PIXEL INTENSITY CONDITION

The following condition is used to check whether a pixel belongs to the selected intensity range:

```python
if rmin <= np.mean(pixel_value) <= rmax:
```

Here:

* `rmin` represents the minimum intensity value.
* `rmax` represents the maximum intensity value.
* `np.mean(pixel_value)` calculates the average intensity of the pixel.
* The condition checks whether the pixel lies within the selected range.

## IMPLEMENTATION

The intensity values are processed using the following logic:

```python
rmin = 100
rmax = 200

if rmin <= np.mean(pixel_value) <= rmax:
    slicing_with_bg[i][j] = 255
    slicing_without_bg[i][j] = 0
else:
    slicing_without_bg[i][j] = 255
```

The output images are then displayed using **Matplotlib**.

## EFFECT OF INTENSITY LEVEL SLICING

Intensity level slicing helps in emphasizing specific regions of an image based on their intensity values.

* **Selected intensity range** → Highlighted
* **Pixels outside the range** → Treated as background
* **With background** → Background information is retained
* **Without background** → Background is suppressed/separated

The choice of intensity range determines which regions of the image are highlighted.

## APPLICATIONS

Intensity level slicing is useful in:

* Image enhancement
* Medical image processing
* Image segmentation
* Feature extraction
* Object detection
* Satellite image analysis
* Industrial image processing
* Digital image analysis

# CONCLUSION

The experiment demonstrates **intensity level slicing** by selecting and highlighting pixels within the intensity range of **100 to 200**. Two different outputs, **slicing with background** and **slicing without background**, are generated to observe the effect of intensity-based pixel selection. This technique helps in emphasizing specific regions of an image and is useful for **image enhancement, segmentation, feature extraction, and digital image processing**.
