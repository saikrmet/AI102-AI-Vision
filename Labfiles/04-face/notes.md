### Azure AI Vision Service: Face Detection and Analysis
*Use Azure AI Vision and Face services to detect, analyze, and recognize faces in images.*

#### Option 1: Using Azure AI Vision with the Analyze Image Function:  
  - Call this function (SDK or REST API) with "People" as a visual feature.
  - In images that contain one or more people, the response includes details of their location in the image and the attributes of the detected person.
  
#### Option 2: Using Face Service Face Detection:  
  - Detects faces in an image and returns:
    - Unique **Face ID** for each face.
    - **Bounding box coordinates** for face location.

- **Face Attribute Analysis**:  
  - Analyze various attributes, including:
    - **Head pose**: Orientation (pitch, roll, yaw).
    - **Glasses**: Types of glasses (NoGlasses, ReadingGlasses, Sunglasses, Swimming Goggles).
    - **Blur**: Level of blur (low, medium, high).
    - **Exposure**: Image exposure (underExposure, goodExposure, overExposure).
    - **Noise**: Amount of visual noise.
    - **Occlusion**: Objects obscuring the face.
    - **Accessories**: Presence of glasses, headwear, masks.
    - **QualityForRecognition**: Face quality for recognition (low, medium, high).

- **Facial Landmark Detection**:  
  - Coordinates for key landmarks (e.g., eye corners, pupils, nose tip).

- **Face Comparison**:  
  - Compare faces in multiple images for:
    - **Similarity**: Determine individuals with similar facial features.
    - **Verification**: Verify that a face in one image matches the same person in another.

- **Facial Recognition**:  
  - Train models to recognize individuals:
    - **Person Group**: Define individuals to identify (e.g., employees).
    - **Add Persons**: Add individuals to the group with detected faces from multiple images.
    - **Persisted Faces**: Face IDs don’t expire after 24 hours.
    - **Model Training**: Use multiple face images (in different poses) to train the model.

- **Facial Liveness Detection**:  
  - Verifies that a video input is real and not spoofed.

- **Face ID Retention**:
- Detected face IDs are unique GUIDs, cached for 24 hours.
- IDs are used for comparison and verification across images during this period.
  
- **Anonymity**:
- Faces can be compared anonymously (useful for verifying that the same person appears at different times without knowing their identity).


#### Training a Facial Recognition Model:
1. **Create a Person Group**: Define a group (e.g., employees) to identify.
2. **Add Persons**: Add individuals to the group.
3. **Add Faces**: Use images with varied poses for each person. These face IDs do not expire (referred to as "persisted faces").
4. **Train the Model**: The trained model is stored in your Azure resource.

- **Usage of Trained Model**:
- **Identify** individuals in images.
- **Verify** a detected face’s identity.