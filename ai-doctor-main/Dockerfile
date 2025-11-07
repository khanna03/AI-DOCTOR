# Use Python base image
FROM python:3.10-slim

# Set working directory
WORKDIR /app

# Install system-level dependencies required for PyAudio & others
RUN apt-get update && apt-get install -y \
    gcc \
    portaudio19-dev \
    ffmpeg \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Copy all project files
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose Gradio port
EXPOSE 7860

# Environment variable (can be set at runtime)
ENV GROQ_API_KEY=""

# Run the app
CMD ["python", "gradio_app.py"]

