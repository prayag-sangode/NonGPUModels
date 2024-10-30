# Use a lightweight Python image
FROM python:3.9-slim

# Set up environment variables to avoid interactive prompts during installation
ENV PYTHONUNBUFFERED=1 \
    PIP_NO_CACHE_DIR=1

# Install the required packages
COPY requirements.txt .
RUN pip install -r requirements.txt

# Copy the application code into the container
COPY app.py /app.py

# Expose the port on which the app will run
EXPOSE 5000

# Run the application
CMD ["python", "/app.py"]
