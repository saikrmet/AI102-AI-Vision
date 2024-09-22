### Azure Video Indexer Service Overview

*Azure Video Indexer helps extract various insights from videos.*

#### Key Features:
- **Facial Recognition**: Detects individuals in videos (requires Limited Access approval).
- **Optical Character Recognition (OCR)**: Reads text from the video.
- **Speech Transcription**: Transcribes spoken dialogue into text.
- **Topic Identification**: Detects key topics discussed in the video.
- **Sentiment Analysis**: Analyzes positive or negative tone of video segments.
- **Labels**: Tags identifying objects or themes throughout the video.
- **Content Moderation**: Detects adult or violent themes in videos.
- **Scene Segmentation**: Breaks down the video into individual scenes.

#### Predefined Models:
- Recognizes **celebrities**, performs **OCR**, and **transcribes speech**.
  
#### Custom Models:
- **People**: Train the model to recognize specific people across videos by providing face images.
- **Language**: Train the model to detect custom terminology specific to your organization.
- **Brands**: Train the model to recognize specific brand names, projects, or companies relevant to your business.

#### Azure Video Indexer Widgets:
- **Embeddable Widgets**: The portal widgets can be embedded into custom HTML interfaces to share video insights without full portal access.

#### Azure Video Indexer API:
- **REST API**: Automate video indexing tasks, retrieve insights, create/delete custom models, etc.
  - **Example API Calls**:
    - Get a logo: `GET https://api.videoindexer.ai/<location>/Accounts/<accountId>/Customization/CustomLogos/Logos/<logoId>?<accessToken>`
    - Get video details: `GET https://api.videoindexer.ai/<location>/Accounts/<accountId>/Videos?<accessToken>`
  
#### Deployment with ARM Templates:
- Use **Azure Resource Manager (ARM) templates** to create the Azure AI Video Indexer resource in your subscription based on predefined parameters.

#### Important Notes:
- To use the API:
  - First, request an **AccessToken** using the **account ID** and **subscription key** found in the API portal.
  - Use the **AccessToken** for subsequent API requests.
  
- For **brand recognition** in conference call videos, edit the **Brands model**, include Bing-suggested brands, and add new brands as needed.