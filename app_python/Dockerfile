# syntax=docker/dockerfile:1

# Use the official image as a parent image
FROM python:3.10-alpine AS build

# Labelling the image
LABEL version="1.0" description="Flask Application showing current Moscow time" maintainer="engaezik"

# Set the working directory
WORKDIR /app_python

# Create user
RUN adduser -D myuser && chown -R myuser /app_python
USER myuser

COPY app.py requirements.txt ./

# Install dependencies
RUN pip install -r requirements.txt --no-cache-dir --user

# Run the application
EXPOSE 5000
CMD [ "python", "-m", "flask", "run", "--host", "0.0.0.0", "--port", "5000"]