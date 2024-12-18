# Skin Cancer Detection

The purpose of this project is to develop a skin cancer detection system aimed at overcoming accessibility challenges in underserved regions. Utilizing International Skin Imaging Collaboration’s SLICE-3D dataset, which consists of smartphone-quality images, the system employs EfficientNet architectures to classify skin lesions as malignant or benign. We compare models trained on high-quality 2019 ISIC data, smartphone-quality 2024 ISIC data, and a fine-tuned transfer learning model to assess their performance. Our results demonstrate the promise of transfer learning in enhancing diagnostic accuracy and specificity, while addressing challenges related to class imbalance and data variability.

## Steps to Set Up and Run the ISIC Skin Cancer Detection Code

1. Clone the repository
2. Update `mdlParams['pathBase']` in `example.py`
    - Navigate to the file: `.\isic2019-master\pc_cfgs\example.py`
    - Open it in a text editor.
    - Find the line where `mdlParams['pathBase']` is defined.
    - Replace it with your current working directory, for example: `mdlParams['pathBase'] = 'CUR_WORKING_DIRECTORY'`
    - Save the changes and close the file.

3. Prepare Data for ISIC 2019
    - Navigate to the directory: `.\isic2019-master\data\isic\2019`
    - Ensure the following files and folders are set up:
        - Indices pickle file: This file should already be in the folder.
        - Images: Add the required images to the image folder. You can download the images from https://challenge.isic-archive.com/data/#2019.
        - Labels CSV: Make sure the label CSV file is inside the image folder.

4. Prepare Data for ISIC 2024
    - Navigate to the directory: `.\isic2019-master\data\isic\2024`
    - Confirm the following files and folders are in place:
        - Indices pickle file: This file should already be in the folder.
        - Images: Add the required images to the image folder. You can download the images from https://www.kaggle.com/competitions/isic-2024-challenge/data.
        - Labels CSV: Ensure the label CSV file is in the image folder.
        - Pretrained Model: Place the best ISIC 2019 model in the pretrained folder. (This model will be generated in step 3)

6. Run the Models
   - Open a terminal or command prompt.
   - Navigate to the project root folder: `cd .\isic2019-master`
   - Use the following commands to execute specific tasks:
       - Run the ISIC 2019 model: `python train.py example isic2019_effb0_ss gpu0`
       - Run the ISIC 2024 model: `python train.py example isic2024_effb0_ss gpu0`
       - Run fine-tuning for ISIC: `python train.py example isic_finetuning_effb0_ss gpu0`

By following these steps, you'll successfully set up and execute the ISIC Skin Cancer Detection models.
