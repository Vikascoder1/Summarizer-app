Instructions for setting up and running the application local
#Prerequisites
//Python: Ensure that Python is installed on your system. You can download it from python.org.

//pip: Make sure pip is installed. It usually comes bundled with Python. 

Setup Instructions
1. Clone the Repository : https://github.com/Vikascoder1/Summarizer-app.git

2. Navigate to the Project Directory : cd app

3. Create a Virtual Environment : 
        python -m venv venv
        venv\Scripts\activate

4. Install the Required Packages:
        pip install -r requirements.txt

5. Run the Streamlit App:
      streamlit run app.py
  
6. Interact with the App
    Upload a PDF, DOCX, or TXT file using the upload interface.
    Click "Summarize" to generate a summary of the uploaded document.

Troubleshooting:
Ensure all dependencies are installed correctly.
Check for any error messages in the terminal for guidance.
If the app doesn’t open automatically, manually navigate to http://localhost:8501 in your web browser.


************************************************************

# Document Summarizer Application

## Overview

This document provides an overview of the approach used to develop the Document Summarizer application, the challenges encountered during its development, and how those challenges were addressed.

## Approach

The Document Summarizer application is a Streamlit-based web app designed to summarize documents in PDF, DOCX, and TXT formats using a pre-trained natural language processing model. The main steps involved in the approach are:

1. **Model Selection**: The `facebook/bart-large-cnn` model from the Hugging Face Transformers library was chosen for its effectiveness in text summarization tasks.

2. **File Handling**: 
   - Used `pdfplumber` for extracting text from PDF files.
   - Used `python-docx` for reading DOCX files.
   - Directly read TXT files as plain text.

3. **User Interface**: Developed using Streamlit, allowing users to upload documents, view original content, and obtain summarized versions through an intuitive interface.

4. **Optimization**: Utilized caching for model loading to enhance performance and added error handling to ensure the application remains robust and user-friendly.

## Challenges and Solutions

### 1. Model Loading Time

**Challenge**: The initial loading time of the summarization model was high, impacting the user experience.

**Solution**: Implemented caching with `@st.cache_resource` to ensure the model is loaded once and reused across multiple requests, significantly reducing the time for subsequent operations.

### 2. Handling Large Documents

**Challenge**: Processing large documents required excessive memory and CPU resources, sometimes leading to application crashes.

**Solution**: Optimized text extraction functions to process and summarize documents in smaller chunks when necessary, reducing the memory footprint and improving performance.

### 3. File Type Compatibility

**Challenge**: Ensuring compatibility and accurate text extraction across different document formats (PDF, DOCX, TXT).

**Solution**: Used specialized libraries (`pdfplumber` for PDFs and `python-docx` for DOCX) to handle specific file types, ensuring accurate and efficient text extraction.

### 4. Error Handling

**Challenge**: Unexpected errors during file processing or summarization could crash the application, disrupting user experience.

**Solution**: Added comprehensive error handling to catch and manage exceptions, providing informative error messages to users while maintaining application stability.

************************************************************

# Bibliography
bibliography lists all relevant open-source software (FOSS) that was forked or referred to during the development of the Document Summarizer application.

## Libraries and Tools

### 1. [Transformers](https://github.com/huggingface/transformers)

### 2. [Streamlit](https://github.com/streamlit/streamlit)

### 3. [pdfplumber](https://github.com/jsvine/pdfplumber)

### 4. [python-docx](https://github.com/python-openxml/python-docx)

### 5. [Hugging Face Model Hub](https://huggingface.co/models)
