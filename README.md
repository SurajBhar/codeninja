# Codeninja: Code Assistant
Codeninja is a local code assistant powered by a custom model named (`codeninja`) hosted using `ollama` and interfaced with a Gradio web application. It enables you to interact with a locally running AI model for coding assistance.

## Demo

Below is a preview of the Codeninja interface in action:

![Codeninja Demo](images/demo.png)

## Features
- Simple interface for coding queries.
- Powered by `codellama` under the hood, named as a custom model (`codeninja`), created and hosted locally.
- Maintains a history of prompts for context-aware responses.
- Uses Gradio for a user-friendly web interface.

## Prerequisites
Before setting up Codellama, ensure you have the following installed:
- [Conda](https://docs.conda.io/projects/conda/en/latest/) (for virtual environment setup)
- [Ollama](https://ollama.com/) (for running the backend model)
- Python (compatible with the dependencies listed in `requirements.txt`)

## Installation

1. **Clone the repository:**
```bash
   git clone https://github.com/SurajBhar/codeninja.git
   cd codeninja
```

2. **Set up a virtual environment:**
```bash
   conda create -n codellama python
   conda activate codellama
```

3. **Install Dependencies:**
The application uses the following Python libraries:

- requests: For interacting with the backend API.
- json: For handling JSON data.
- gradio: For creating the web interface.

```bash
   pip install -r requirements.txt
```

4. **Download the codellama:**
- Make sure you have downloaded the Ollama.
- Go to terminal and run following command:
```bash
ollama run codellama
```

5. **Set up the model:**
Go to terminal, change directory to codellama where ``modelfile`` is present and run:
```bash
   ollama create codeninja -f modelfile
```

6. **Run the application:**
Make sure you are in the right directory ``codeninja`` and run:
```bash
   python app.py
```

## Directory Structure
```
codeninja/
├── app.py               # Main application file
├── modelfile            # Model configuration file
├── requirements.txt     # Dependencies
└── README.md            # Project documentation
└── demo.png             # Project demonstration

```

## Code Explanation:
``app.py``
- Backend URL: The application interacts with a locally hosted API (http://localhost:11434/api/generate) using requests.
- Custom Model: Requests are sent to the codeninja model hosted on Ollama.
- Prompt History: Maintains a history of prompts to provide context-aware responses.
- Gradio Interface: Creates a simple web interface with a text input and a text output for user interaction.

## Key Functionality
``generate_response(prompt):``
- Takes a user prompt, appends it to the history for context, and sends a request to the backend API. 
- Returns the AI-generated response or logs an error if the API request fails.

## Gradio Interface:
- Input: A multi-line text box for user prompts.
- Output: A text display for the generated responses.
- Launch: Opens the interface on a local server.

## Usage
- Enter your coding-related queries into the input box.
- View the AI-generated responses in real-time.
- The assistant retains a history of previous prompts for better contextual understanding.

## Troubleshooting
- Model not running: Ensure the codeninja model is created and running via Ollama.
- API connection issues: Verify the backend URL (http://localhost:11434) is correct and accessible.
- Dependency issues: Check that all dependencies in requirements.txt are installed.

# Contributing
Contributions are welcome! Feel free to fork this repository and submit pull requests for enhancements or bug fixes.

# Acknowledgments
- Ollama for enabling local model hosting.
- Gradio for the interactive web interface.
