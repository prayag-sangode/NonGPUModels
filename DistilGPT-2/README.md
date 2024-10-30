```markdown
# DistilGPT-2 Text Generation API

This project provides a simple text generation API using the DistilGPT-2 model from Hugging Face's Transformers library. The API is built with Flask and allows users to generate text based on a provided prompt.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoint](#api-endpoint)
- [Requirements](#requirements)
- [Docker](#docker)
- [License](#license)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/DistilGPT-2.git
   cd DistilGPT-2
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Run the Flask application:
```bash
python app.py
```
The application will start on `http://localhost:5000`.

## API Endpoint

### Generate Text

**POST** `/generate`

**Request Body:**
```json
{
  "prompt": "Once upon a time",
  "max_length": 50
}
```

**Response:**
```json
{
  "generated_text": "Once upon a time..."
}
```

### Make API Calls

Use `curl` or a similar tool to send POST requests to your `/generate` endpoint:
```bash
curl -X POST "http://localhost:5000/generate" \
     -H "Content-Type: application/json" \
     -d '{
          "prompt": "Once upon a time",
          "max_length": 50
     }'
```

## Requirements

The following packages are required:
- Flask
- Transformers
- Torch (optional if CPU version of Transformers requires it)

## Docker

To run the application in a Docker container, follow these steps:

1. Build the Docker image:
   ```bash
   docker build -t distilgpt2-app .
   ```

2. Run the Docker container:
   ```bash
   docker run -p 5000:5000 distilgpt2-app
   ```

The application will be accessible at `http://localhost:5000`.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```
