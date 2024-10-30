# DistilGPT-2 Text Generation API

This project provides a simple REST API using Flask that generates text based on a given prompt using the DistilGPT-2 model from Hugging Face's Transformers library.

## Overview

DistilGPT-2 is a smaller, faster, and lighter version of the GPT-2 model. It retains much of the performance while being more efficient, making it suitable for various applications in text generation. This API allows users to input a prompt and receive a continuation of that prompt as generated text.

## Features
- **Text Generation**: Generate coherent text based on user-provided prompts.
- **Flexible Length**: Specify the maximum length of the generated text.
- **Lightweight**: Built using a slim Python image for Docker, optimizing the application's footprint.

## Requirements

- Docker
- Python 3.9+
- Required Python libraries specified in `requirements.txt`

## Installation

1. Clone the repository:

   ```bash
   git clone <repository_url>
   cd DistilGPT-2
   ```

2. Build the Docker image:

   ```bash
   docker build -t distilgpt2-app .
   ```

3. Run the Docker container:

   ```bash
   docker run -p 5000:5000 distilgpt2-app
   ```

## Usage

To generate text, send a POST request to the `/generate` endpoint with a JSON body containing the `prompt` and an optional `max_length` parameter.

### Example Request

Using `curl`, you can generate text as follows:

```bash
curl -X POST "http://localhost:5000/generate" \
     -H "Content-Type: application/json" \
     -d '{
          "prompt": "Once upon a time",
          "max_length": 50
     }'
```

### Example Response

```json
{
  "generated_text": "Once upon a time when the world is not just a little different after all, we can all get in the groove, and we never get all stuck, either. With time and energy remaining, in the case of our mind, we should all be..."
}
```

## How It Works

1. **Flask App**: The application is built using Flask, a lightweight web framework for Python.
2. **Text Generation**: The `transformers` library is utilized to load the DistilGPT-2 model and generate text.
3. **API Endpoint**: The `/generate` endpoint handles incoming POST requests and returns the generated text as a JSON response.

## Use Cases

- **Creative Writing**: Use the model to assist in story writing or brainstorming ideas.
- **Chatbots**: Integrate the API into chatbots for generating responses based on user prompts.
- **Content Generation**: Generate articles, summaries, or social media posts automatically.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```
