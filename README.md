# Sentiment-Analysis-using-Hugging-Face

This project is a simple FastAPI-based application that provides sentiment analysis for any input text. It uses a pre-trained Hugging Face model (`distilbert-base-uncased-finetuned-sst-2-english`) to classify the sentiment of the text. The sentiment is classified as either "positive" or "negative", and the response includes a sentiment label along with a confidence score.

## Features

- **Sentiment Analysis**: Uses a pre-trained model to analyze the sentiment of the input text.
- **API Endpoint**: Exposes a POST endpoint `/sentiment` that accepts a JSON body with a string input and returns the sentiment label and score.
- **Dockerized**: The application is fully containerized with Docker, making it easy to deploy anywhere.

## Technologies Used

- **FastAPI**: A modern, fast web framework for building APIs with Python.
- **Hugging Face Transformers**: Provides state-of-the-art natural language processing (NLP) models.
- **Docker**: For containerizing the application and making it portable and easy to deploy.

## Installation and Setup

### 1. Clone the repository

Clone the repository to your local machine:

```bash
git clone https://github.com/varun7778/Sentiment-Analysis-using-Hugging-Face.git
cd Sentiment-Analysis-using-Hugging-Face
```

### 2. Install Dependencies

Create a virtual environment and install the required Python dependencies:

```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

Alternatively, you can use Docker if you prefer to avoid setting up the environment manually.

### 3. Running the API Locally

Once dependencies are installed, you can run the FastAPI server locally using Uvicorn:

```bash
uvicorn app:app --reload
```

By default, the application will be available at [http://localhost:8000](http://localhost:8000).

You can test the API by sending a POST request to `/sentiment` with a JSON body containing an `input` field.

### 4. Docker Setup

Alternatively, you can run the application inside a Docker container. This is especially useful for deployment or if you want a quick, reproducible setup.

#### Step 1: Build the Docker Image

From the root directory of the project, build the Docker image:

```bash
docker build -t sentiment-analysis-api .
```

#### Step 2: Run the Docker Container

After building the image, you can run the container:

```bash
docker run -p 8000:8000 sentiment-analysis-api
```

The API will now be running in a container and accessible at [http://localhost:8000](http://localhost:8000).

## Project Structure

```
├── app.py                # Main FastAPI app file
├── Dockerfile            # Dockerfile to containerize the app
├── requirements.txt      # Python dependencies
└── README.md             # This README file
```
