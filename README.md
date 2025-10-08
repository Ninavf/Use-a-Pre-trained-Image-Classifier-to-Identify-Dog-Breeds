# Use-a-Pre-trained-Image-Classifier-to-Identify-Dog-Breeds
Use a pre-trained image classifier to identify dog breeds — first project for the AI Programming with Python course by Coursera.
This project classifies pet images using pretrained Convolutional Neural Networks (CNNs) like **ResNet**, **AlexNet**, and **VGG16**. It also compares model predictions to true labels extracted from image filenames to evaluate accuracy.

---

                           ## Step Process of the Image Classifier
### 1. `get_input_args.py`
- Reads input from the command line or uses default values.  
- Determines:
  - Image folder path  
  - CNN architecture to use  
  - Dog names file (for reference)
  Explanation:
  - `--dir`: Path to the image folder (default: `pet_images/`)
  - `--arch`: CNN architecture to use (default: `alexnet`)
  - `--dogfile`: File containing valid dog names (default: `dognames.txt`)  

### 2. `get_pet_labels.py`
- Extracts true labels from image filenames.  
- Stores labels in a dictionary for later comparison with predictions.
Explanation: Extracts the true label of each image from its filename. For example, `Boston_terrier_02259.jpg` → `"boston terrier"`. These labels are later used for accuracy comparison.

### 3. `classifier.py`
- Loads each image.  
- Preprocesses it according to the chosen pretrained CNN requirements.  
- Runs the image through the pretrained model to generate a predicted label.
Explanation: Contains a function that takes an image path and a model name. It loads the image, preprocesses it to match the CNN requirements, runs it through the selected pretrained model, and returns a human-readable label.

### 4. `classify_images.py`
- Compares CNN predictions with the true labels obtained in step 2.  
- Stores the predicted label and a match indicator (`1` for match, `0` for no match) in `results_dic`.
Explanation: Compares the CNN predictions to true labels obtained from the image filenames. Adds predictions and match results to a dictionary (`results_dic`) for each image.

### 5. `print_functions_for_lab_checks.py` (optional/debugging)
- Displays intermediate results for verification.  
- Checks a few predictions, matches, and pet labels to ensure the process is correct.

### 6. `print_results.py`
- Summarizes results and statistics, including:
  - Accuracy  
  - Number of correctly classified dogs  
  - Other relevant metrics  
- Presents the final outcomes clearly.
