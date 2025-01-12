# Use the official Python image from the Docker Hub
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Install dependencies required to create a virtual environment
RUN apt-get update && apt-get install -y python3-venv

# Copy the current directory contents into the container at /app
COPY . /app

# Create the virtual environment
RUN python3 -m venv venv

# Install any needed packages specified in requirements.txt using the virtual environment's pip
RUN ./venv/bin/pip install --no-cache-dir -r requirements.txt

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable
ENV FLASK_ENV=development

# Run app.py using the virtual environment's python
CMD ["./venv/bin/python", "app.py"]