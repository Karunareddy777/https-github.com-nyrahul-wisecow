1.Clone the repository git clone
https://github.com/nyrahul/wisecow

2.write the Dockerfile:

# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME Wisecow

# Run app.py when the container launches
CMD ["python", "app.py"]

3.Bulid a docker image:
docker build -t wisecow-app .

4.Test the docker image locally:
docker run -p 8080:80 wisecow-app
