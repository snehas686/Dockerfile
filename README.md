# Dockerfile
# Use an official Python runtime as the base image
FROM python:3.10-slim

# Set environment variables (prevents Python from buffering output)
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container
COPY . /app/

# Install any required dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose the port the app will run on
EXPOSE 8000

# Command to run the application (adjust according to your app's entry point)
CMD ["python","app.py"]
