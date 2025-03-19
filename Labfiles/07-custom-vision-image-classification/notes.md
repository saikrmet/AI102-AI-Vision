### Creating an Azure AI Custom Vision Solution  

Azure AI Custom Vision allows you to train models to recognize and classify images.  

#### Two Main Tasks in Custom Vision  

1. Train a model using labeled images.  
2. Deploy and use the model by creating a client application that submits new images for predictions.  

#### Required Azure Resources  

To use Azure AI Custom Vision, you need two types of resources.  

**Training Resource Options**  

- Azure AI Services Multi-Service Resource  
- Azure AI Custom Vision Training Resource  

**Prediction Resource Options**  

- Azure AI Services Multi-Service Resource  
- Azure AI Custom Vision Prediction Resource  

You can use a multi-service resource for both training and prediction. You can also mix resource types. For example, you can use a Custom Vision Training Resource to train a model and then publish it using an Azure AI Services Multi-Service Resource.  

If using a multi-service resource, the key and endpoint for both training and prediction will be the same.  

