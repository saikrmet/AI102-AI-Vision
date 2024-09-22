### Azure AI - Text Recognition Features

*Azure AI provides two OCR features optimized for different document types and use cases.*

#### 1. **Image Analysis OCR (Azure AI Vision Service)**
- **Use Case**: General, unstructured documents with smaller amounts of text or images with text.
- **Examples**: Street signs, handwritten notes, store signs.
- **Operation**:
  - **Synchronous** results from a single API call.
  - Extracts text and performs additional image analysis (e.g., object detection, categorizing images).
- **OCR Results**:
  - Results broken into blocks, lines, and words.
  - Text values available at both line and word levels for easier reading.
- **Recommended for**: Handling short sections of handwritten text in multiple languages.
- **API Call**:
  - Use `ImageAnalysis` function.
  - Specify image URL or binary data.
  - Optionally, include a language code (default: `en` for English).
  - Specify visual feature as `READ` for OCR.

#### 2. **Document Intelligence**
- **Use Case**: Reading large volumes of text from images and PDF documents.
- **Examples**: Receipts, articles, invoices.
- **Operation**:
  - **Asynchronous** process.
  - Initial function returns an operation ID, which is used to retrieve results later.
- **Enhanced Accuracy**:
  - Utilizes document context and structure to improve accuracy.
  - Suitable for structured documents with more text.

#### Key Differences:
- **Image Analysis OCR**:
  - Synchronous, immediate results.
  - Optimized for unstructured text in images.
  - Additional image analysis features.
  
- **Document Intelligence**:
  - Asynchronous, suited for larger, structured documents.
  - Enhanced accuracy for documents like invoices or receipts.

#### Choosing the Right Service:
- **For unstructured images or small text snippets** (e.g., handwritten notes): Use **Image Analysis OCR** in Azure AI Vision.
- **For large, structured documents** (e.g., invoices or articles): Use **Document Intelligence**.