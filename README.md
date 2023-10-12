# Hate Speech Detection in Slovak Language

This project focuses on "Hate Speech Detection" in the Slovak language using machine learning. Hate speech detection involves the process of identifying and recognizing hate speech within text, audio, or image data using computer programs or artificial intelligence systems. With the growing use of social media, content moderation has become increasingly crucial. This technology is used to detect hate speech on various social platforms. While there have been numerous research studies and models developed in this field, it was observed that there was no model specifically designed for the Slovak language. Consequently, a project was initiated to design an artificial intelligence model primarily focused on the Slovak language and eventually supporting multiple languages.

## Dataset

The original dataset was collected from Twitter and consists of tweets labeled as 'positive,' 'negative,' or 'neutral.'

- The original dataset is stored in the 'raw_data.xlsx' file.
- Other datasets were derived from the original dataset.

  - 'imbalanced_filtered_dataset': Tweets are labeled as 'offensive (1)' or 'non-offensive (0)' and have been filtered.

  - 'balanced_filtered_dataset': Tweets are labeled as 'offensive (1)' or 'non-offensive (0)' and have been filtered and balanced using up-sampling.

  - 'feature_added_imbalanced_filtered_dataset': Tweets are labeled as 'offensive (1)' or 'non-offensive (0)' and have been filtered to include various features.

## Model Evaluation

### Model1.py

- Epoch: 10
- Batch Size: 32
- Learning Rate: 1e-3
- Dropout: 0.1

**Model Definition:**
- 2 Dropout Layers
- 2 Dense Layers

### Model2.py

- Epoch: 10
- Batch Size: 32
- Learning Rate: Scheduled (starts from 1e-3)
- Dropout: 0.1

**Model Definition:**
- 4 Dropout Layers
- 4 Dense Layers

### Model3.py

- Cross-Validation with Model2
- Epoch: 5
- Batch Size: 32
- Learning Rate: Scheduled
- Dropout: 0.1

**Model Definition:**
- 4 Dropout Layers
- 4 Dense Layers

### Model4.py

- Epoch: 20
- Batch Size: 32
- Learning Rate: Scheduled (starts from 2e-3)
- Dropout: 0.1

**Model Definition:**
- 4 Dropout Layers
- 4 Dense Layers
- 3 BatchNormalization Layers

### Result

|     | Precision | Recall  | F1-Score | Support |
|----- | ---------- | ------- | -------- | ------- |
|  0 (Non Offensive) |    0.88    |  0.55   |   0.68   |  2630   |
|  1 (Offensive)|    0.67    |  0.92   |   0.78   |  2632   |
#
|     | Precision | Recall  | F1-Score | Support |
|----- | ---------- | ------- | -------- | ------- |
Accuracy |          |   0.74   |  5262   |
Macro Avg |  0.78   |   0.74   |  0.73   |  5262   |
Weighted Avg |  0.78   |   0.74   |  0.73   |  5262   |
