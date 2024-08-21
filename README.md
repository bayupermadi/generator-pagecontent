# PDF to DOCX Content Generator

This simple Flask application helps you convert any PDF source file into a DOCX document that you can use for website content. The application leverages OpenAI's ChatGPT (via the OpenAI API) to extract topics from the PDF and generate detailed, well-structured content.

## Features

- **PDF to DOCX Conversion**: Automatically converts a PDF file into a DOCX document with content suitable for website use.
- **AI-Powered Content Generation**: Utilizes OpenAI's GPT-4 to extract the main topic from the PDF and generate detailed content.
- **Configurable Prompts**: Easily customize the prompts and other settings via a YAML configuration file.

## Getting Started

Follow these instructions to set up and run the application on your local machine.

### Prerequisites

Ensure that you have the following installed:

- Python 3.6 or higher
- pip (Python package installer)

### Setup Instructions

1. **Clone the Repository**

   Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/pdf-to-docx-content-generator.git
   cd pdf-to-docx-content-generator

2. **Install Dependencies**

   Install the necessary Python packages using pip:
   ```bash
   pip install -r requirements.txt

3. **Set Up the Configuration File**

    - Rename the `config.yaml-templat`e file to `config.yaml`:
    
      ```bash
      Copy code
      mv config.yaml-template config.yaml
    
    - Open the config.yaml file in a text editor and fill in the required information:
    
      ```yaml
      Copy code
      app:
        host: "0.0.0.0"
        port: 5000
        debug: true
      
      openai:
        api_key: "YOUR_OPENAI_API_KEY_HERE"
        model: "gpt-4"
      
      prompts:
        topic_extraction:
          system_message: "You are an assistant that identifies main topics from texts."
          user_message: "Please identify the main topic of the following text:"
          max_tokens: 50
          temperature: 0.5
      
        content_generation:
          system_message: "You are a skilled content writer who creates informative and well-structured articles."
          user_message: "Write a comprehensive, well-organized, and informative article about '{topic}'. The article should be approximately 3000 words, include relevant subheadings, and provide valuable insights on the topic."
          max_tokens: 3500
          temperature: 0.7
    - API Key: Replace "YOUR_OPENAI_API_KEY_HERE" with your actual OpenAI API key.
    
    - Customize Prompts: Adjust the prompts in the prompts section to suit your needs.

4. **Run the Application**

    Start the Flask application:
    
    ```bash
    Copy code
    python app.py
    ```
    
    The application will be available at http://localhost:5000/ by default, or at http://<your-ip>:5000/ if accessed from another machine.

5. **Upload a PDF and Generate Content**

    - Open your web browser and navigate to the application URL.
    - Use the provided form to upload a PDF file.
    - The application will process the PDF, extract the main topic, generate content, and provide a DOCX file for download.
      
## License ##

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing ##

Feel free to submit issues, fork the repository, and create pull requests. Contributions are welcome!

