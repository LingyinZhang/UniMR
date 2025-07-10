# UniMR User Guide

This software is designed to segment, enhance, and match molecular images using image processing and machine learning techniques. Users can upload molecular images, select target molecules, and obtain classification results.

## Dependency

To use our software, you need to use the following systems and python version.

- Operating System: Windows
- Python Version: Python 3.9 or higher

We suggest that you run the software in a virtual environment like `conda create -n unimr python=3.9` 

Please install the necessary dependencies through `pip install -r requirements.txt` .

Please note that the "models" folder is used to store the clip models used by the software. They can be automatically downloaded by running the software or manually downloaded through the website [ViT-B-32.pt](https://openaipublic.azureedge.net/clip/models/40d365715913c9da98579312b702a82c18be219cc2a73407c4526f58eba950af/ViT-B-32.pt).

Now you can run the software through `python GUI.py`.

The CUDA version used in the test is 12.4. For detailed instructions on installing CUDA, please refer to https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html.

## Usage

This section will introduce how to use the UniMR software.

1. **Launch the UniMR Software**

   Upon running the software, the Start Window will appear. Ensure that your Python environment is properly configured and that all dependent libraries are installed.

2. **Load Molecular Images**

   In the Start Window, click the "Select Image Path" button to select the file path containing the target molecular image, and then clik "Confirm" button. The software will load the image and display it in the Segmentation Window.

3. **Resize the segmentation**

   In the Segmentation Window, you can adjust the segmentation effect through the Threshold, Min Area, and Max Area. The functions of the three sliders are as follows. After adjusting, click the "Apply Settings" button to enter the Labeling and Classification Window.

   + **Threshold**: *Adjusts the brightness threshold for detecting objects.*
   + **Min Area (%)**: *Sets the minimum size of detected objects as a percentage of the image area.*
   + **Max Area (%)**: *Sets the maximum size of detected objects as a percentage of the image area.*

4. **Label Target Molecules**

   In the Labeling and Classification Window, click the "Select Target Molecule" button, then click on the molecule you want to use as a sample in the image. The software will prompt you to enter the target molecule's name and color. Red, Green and Blue respectively represent the three primary colors of RGB. Please enter an integer between 0 and 255. After entering the details, click the "Submit" button, then the target molecule will be marked and saved. Multiple targets can be selected one by one. The options on the right default to the Settings applied in the paper. You can also adjust them by yourself. 

5. **Classify Molecules**

   Click the "Start Classification" button to start classifying, and the software will vectorize all molecules and match them with the target molecules. If the match result is above the set threshold, the molecule will be classified as the corresponding target molecule; otherwise, it will be classified as "other".

6. **View Results**

   Please wait patiently. When the classification is completed, the software will pop up a Classification Results Window showing the quantity of each type of molecule.
