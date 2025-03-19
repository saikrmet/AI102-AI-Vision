### **Labeling Images for Object Detection in Azure AI Custom Vision**  

Azure AI Custom Vision provides an interactive interface for labeling images, making object detection easier and more efficient.  

#### **Using the Azure AI Custom Vision Portal**  

- The portal provides an interactive interface for tagging images.  
- It suggests regions where objects are located.  
- Users can assign tags or adjust bounding boxes by dragging them.  

#### **Smart Labeling for Faster Annotation**  

- After tagging an initial set of images, you can train the model.  
- The **smart labeler tool** helps label new images by suggesting both object regions and their classes.  

#### **Using External Labeling Tools**  

- **Azure Machine Learning Studio** and **Microsoft Visual Object Tagging Tool (VOTT)** allow additional features, such as assigning tasks to multiple team members.  

#### **Bounding Box Measurement Units**  

- If using an external labeling tool, adjust the bounding box format to match **Azure AI Custom Vision API** requirements.  
- Bounding boxes are defined by four proportional values:  
  - **Left (X):** Distance from the left edge of the image.  
  - **Top (Y):** Distance from the top edge of the image.  
  - **Width:** Proportional width of the bounding box.  
  - **Height:** Proportional height of the bounding box.  

#### **Example Bounding Box Values**  

| Parameter | Value | Explanation |  
|-----------|-------|------------|  
| Left | 0.1 | Box starts at one-tenth of the image width from the left. |  
| Top | 0.5 | Box starts at half the image height from the top. |  
| Width | 0.5 | Box spans half of the image width. |  
| Height | 0.25 | Box spans one-quarter of the image height. |  
