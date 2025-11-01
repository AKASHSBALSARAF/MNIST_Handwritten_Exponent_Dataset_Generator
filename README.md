# MNIST Handwritten Exponent Dataset Generator

This is my small project where I made a dataset generator using MNIST digits to create images of handwritten exponents.  
Basically, it takes normal MNIST digits, crops them properly, and then combines one digit as a base and another as an exponent (like 2⁵ or 7³).  
All the images are saved along with a CSV file that has labels and coordinates of the exponent.

---

## What this project does

1. Crops MNIST digits to remove extra black borders.  
2. Makes small exponent digits (12x12 size).  
3. Combines both base and exponent digits on a 64x64 canvas.  
4. Applies small random shifts, rotations, and blur to make them look handwritten.  
5. Saves the final images and creates a CSV file with all labels.

---

## Folder Structure

- mnist_cropper.ipynb # Code to crop MNIST digits
- exponent_dataset_generator.ipynb # Code to combine digits and create dataset
- cropped_mnist_digits/ # Contains cropped MNIST samples (10 samples added)
- exponent_digits/ # Smaller digits created by the program
- combined_dataset/ # Final base + exponent samples (10 samples added)
- annotations.csv # Labels for generated images
---

## Example Images

| Cropped MNIST Digit | Combined Base+Exponent |
|---------------------|------------------------|
| ![Cropped MNIST Digit](cropped_mnist_digits/mnist_0_5.png) | ![Combined](combined_dataset/combined_0.png) |
| ![Cropped MNIST Digit](cropped_mnist_digits/mnist_5_2.png) | ![Combined](combined_dataset/combined_3.png) |

---

## How to Run

### Step 1: Install dependencies
You can install everything from `requirements.txt`:
```bash
pip install -r requirements.txt
```

### Step 2: Run MNIST Cropper
This will load the MNIST dataset and save cropped digits inside `cropped_mnist_digits/`.

Open the notebook `mnist_cropper.ipynb` in Jupyter and run the cells, or run the script version:

```bash
# If you prefer running as a Python script
python mnist_cropper.py
```

If you are using the notebook, just run the cells; it will save cropped images into the `cropped_mnist_digits/` folder.

### Step 3: Run Exponent Dataset Generator
This part combines base and exponent digits, applies some effects, and saves the final dataset and annotations file.

```bash
jupyter notebook exponent_dataset_generator.ipynb
```

Or run as a script:

```bash
python exponent_dataset_generator.py
```

---

## About the Output

- The images are 64x64 pixels, grayscale.
- Each image has one main digit and one small digit in the top-right corner like an exponent.
- The CSV file `annotations.csv` looks something like this:

| base_digit | exponent_digit | image_path | exp_x | exp_y |
|-------------|----------------|-------------|-------|-------|
| 7 | 2 | combined_dataset/combined_001.png | 38 | 10 |

---

## Requirements

- tensorflow  
- numpy  
- pandas  
- opencv-python  
- pillow  
- tqdm  
- matplotlib  

All mentioned in `requirements.txt`.

---
