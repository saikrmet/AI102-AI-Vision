### Image Classification and Object Detection
*Creating a custom Azure AI Vision model involves preparing a dataset, labeling images, and training the model to classify or detect objects in images.*

#### Image Classification
- **Definition**: Predicts a label for an entire image based on its content.
- **Types**:
  - **Multi-class**: Image belongs to one class.
  - **Multi-label**: Image can belong to multiple classes.

#### Object Detection
- **Definition**: Detects the presence and location of one or more objects in an image.
- **Types**: Similar to image classification, it supports multi-class and multi-label detection.

#### Components of a Custom Vision Project
- **Dataset**:
  - Collection of images stored in Azure Blob Storage.
  - **COCO File**: JSON file that defines image locations, annotations, and categories.

- **Training Process**:
  1. **Upload Images**: Store training images in a blob storage container.
  2. **Create Dataset**: Define the dataset type (e.g., image classification, object detection).
    - You can either create a dataset using Vision Studio by going to the custom model tile or you can use REST:
    ```
    curl -X PUT https://<endpoint>/computervision/datasets/<dataset-name>?api-version=<version>\
        -H "Content-Type: application/json" \
        -H "Ocp-Apim-Subscription-Key: <subscription-key>" \
        --data-ascii "
        {
            'annotationKind':'imageClassification',
            'annotationFileUris':['<URI>']
        }"
  ```
  3. **Label Images**: You can use Azure Machine Learning Studio for accurate labeling, which generates the COCO file or upload the COCO file using REST.
  4. **Train the Model**: Select the model type, specify the dataset, and set the training budget.
  5. **Evaluate Performance**: Check the model's performance using evaluation datasets and iterate if necessary.

#### COCO File Details
- **Images**: Includes location, size, and ID.
- **Annotations**: Defines classifications, categories, and bounding boxes for object detection.
- **Categories**: IDs for each label class.

#### Training and Evaluation
- **Labeling**: Accurate and complete labeling improves model performance.
- **Training Budget**: Upper bound on time allocated for training the model.
- **Evaluation**: Use a subset of labeled images to evaluate model performance.

#### Labeling and COCO File Integration
- **Labeling Tools**: Azure Machine Learning provides tools like ML-assisted labeling.
- **Object Detection**: Each annotation in the COCO file also contains a bounding box array with the values in the array being Left, Top, Width, and Height.
- **Adding COCO File**: Once labeling is complete, integrate the COCO file into your dataset.

#### Final Steps
- **Model Usage**: Once trained and evaluated, the model can be deployed in Vision Studio or integrated into your application for image classification or object detection tasks.