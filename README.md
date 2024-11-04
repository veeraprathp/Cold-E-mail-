# Cold Mail Generator

This application is a **Cold Mail Generator** built using Python, Streamlit, and the LangChain framework. The purpose of this tool is to help job seekers automatically generate personalized cold emails tailored to specific job postings. This project is designed to extract job details from career websites, understand the job requirements, and compose an email showcasing relevant skills and experience for the job seeker.

## Features

- **Job Posting Extraction**: Scrapes job details from a specified URL and extracts information such as job role, experience, skills, and description.
- **Cold Email Generation**: Automatically generates a personalized email, highlighting relevant skills, experience, and projects, based on the job details.
- **Portfolio Link Matching**: Uses keywords from the job description to retrieve relevant portfolio links, providing a customized showcase in the email.

## Tech Stack

- **Python**
- **Streamlit**: Provides a user-friendly interface.
- **LangChain and ChatGroq**: Powers the natural language understanding and generation capabilities.
- **Dotenv**: For loading environment variables, specifically the Groq API key.
- **pypdf**: Extracts text from PDFs if used in the project (potential future extension).
- **OpenAI API (optional)**: Could be used for text-to-speech and other advanced text generation features.

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/cold-mail-generator.git
   cd cold-mail-generator
   ```

2. **Environment Variables**:
   - Create a `.env` file in the root directory and add your **Groq API key**:
     ```plaintext
     GROQ_API_KEY=your_groq_api_key_here
     ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Application**:
   ```bash
   streamlit run main.py
   ```

5. **Access the Application**:
   - Open the app in your browser at `http://localhost:8501`.

## File Overview

### 1. `main.py`
- **Purpose**: This is the main entry point for the application. It defines the Streamlit app structure and the input/output flow.
- **Key Functions**:
  - `create_streamlit_app`: Sets up the Streamlit UI for inputting a job URL and triggering the email generation process.
  - Uses instances of the `Chain` and `Portfolio` classes to process job information and generate the email.

### 2. `chains.py`
- **Purpose**: This file contains the `Chain` class, which is responsible for handling language generation tasks with LangChain.
- **Key Functions**:
  - `extract_jobs`: Scrapes and extracts structured job information from a given webpage.
  - `write_mail`: Generates a personalized cold email based on the provided job description and links.

### 3. `portfolio.py`
- **Purpose**: Manages the job seeker's portfolio links.
- **Usage**: Can query links based on job skills to provide tailored links for inclusion in cold emails.

### 4. `utils.py`
- **Purpose**: Contains utility functions like `clean_text` for pre-processing text from scraped web content.

## Usage Instructions

1. **Enter a URL**: Input the URL of a job posting on a company’s careers page.
2. **Generate Email**: Click "Submit" to extract job details and generate a cold email tailored to the job description.
3. **View the Email**: The generated email will be displayed in Markdown format, ready to be sent or further customized.

## Requirements

- Python 3.8+
- Streamlit
- LangChain
- Environment variables setup for `GROQ_API_KEY`

## Future Enhancements

- **Text-to-Speech**: Convert generated emails into audio using the OpenAI TTS API.
- **Job Posting Caching**: Cache previously scraped job postings for faster future retrieval.
- **Enhanced Personalization**: Use additional information like past job applications or user feedback to refine email content.

## Troubleshooting

- **Environment Variable Errors**: Ensure the `.env` file is correctly configured with your `GROQ_API_KEY`.
- **Missing Dependencies**: Run `pip install -r requirements.txt` to install all required packages.
- **Streamlit Errors**: Ensure Streamlit is correctly installed; try reinstalling with `pip install streamlit`.

## Contributing

Contributions to improve the project are welcome! Please submit a pull request or open an issue to discuss proposed changes.

## License

This project is licensed under the MIT License.
