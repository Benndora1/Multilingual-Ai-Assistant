# AI Voice Assistant

An interactive AI assistant that combines speech recognition, text-to-speech capabilities, and the Gemini AI model to create a conversational interface. The application allows users to speak commands, processes them through Google's Gemini AI, and receives audio responses.

## Features

- Speech recognition for voice input
- Integration with Google's Gemini AI model
- Text-to-speech conversion for responses
- Interactive Streamlit web interface
- Logging system for error tracking and debugging
- Downloadable audio responses

## Dependencies

The project uses several Python libraries:

- **speech_recognition**: Handles voice input and speech recognition
  - Used for converting speech to text
  - Utilizes Google's speech recognition service

- **logging**: Manages application logging
  - Tracks errors and application events
  - Creates organized log files with timestamps

- **gtts (Google Text-to-Speech)**: Converts text responses to speech
  - Generates natural-sounding speech from text
  - Supports multiple languages (currently set to English)

- **google.generativeai**: Interfaces with Google's Gemini AI model
  - Processes natural language queries
  - Generates contextual responses

- **streamlit**: Creates the web interface
  - Provides interactive UI elements
  - Handles audio playback and file downloads

- **python-dotenv**: Manages environment variables
  - Secures API keys and sensitive data
  - Loads environment variables from .env file

## Project Structure

```
project_root/
│
├── .env                    # Environment variables (API keys)
├── main.py                # Main application file
├── logs/                  # Log directory
│   └── application.log    # Application logs
└── speech.mp3             # Generated speech output
```

## Functions and Components

### 1. Logging Setup
```python
LOG_DIR = "logs"
LOG_FILE_NAME = "application.log"
```
- Creates a logging directory and file
- Records timestamps, log levels, and messages

### 2. Voice Input (takeCommand)
```python
def takeCommand():
    """
    Captures and processes voice input
    Returns: text as query
    """
```
- Initializes speech recognizer
- Captures audio from microphone
- Converts speech to text
- Handles recognition errors

### 3. Text-to-Speech (text_to_speech)
```python
def text_to_speech(text):
    """
    Converts text to speech
    Saves output as MP3
    """
```
- Takes text input
- Generates audio file
- Saves as speech.mp3

### 4. AI Model Integration (gemini_model)
```python
def gemini_model(user_input):
    """
    Processes input through Gemini AI
    Returns: AI-generated response
    """
```
- Configures Gemini AI
- Processes user input
- Returns generated response

### 5. Main Application Interface
```python
def main():
    """
    Handles main application flow
    Creates Streamlit interface
    """
```
- Creates web interface
- Manages user interactions
- Displays responses and audio

## Setup and Installation

1. Clone the repository
2. Install required packages:
```bash
pip install speech_recognition gtts google-generativeai streamlit python-dotenv
```
3. Create a `.env` file with your Gemini API key:
```
GEMINI_API_KEY=your_api_key_here
```
4. Run the application:
```bash
streamlit run main.py
```

## Usage

1. Click "Ask me anything!" button
2. Speak your question/command
3. Wait for the AI to process and respond
4. Listen to the response or download the audio file

## Error Handling

- Speech recognition errors are logged and handled gracefully
- API errors are captured and logged
- User feedback is provided for all error states

## Security Considerations

- API keys are stored in environment variables
- Logs are stored locally
- Audio files are temporary and overwritten

## Future Improvements

- Add support for multiple languages
- Implement conversation history
- Add more voice customization options
- Improve error handling and recovery
- Add unit tests and documentation

---

**Note**: Remember to keep your API keys secure and never commit them to version control.
