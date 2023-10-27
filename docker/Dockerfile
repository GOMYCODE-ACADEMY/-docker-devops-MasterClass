# Choose the environment for the app: Python 3.6
FROM python:3.6-alpine

# Set the working directory inside the container to /opt
WORKDIR /opt

# Copy all files from the current directory inside the container
COPY . /opt/

# Install the dependencies listed in requirements.txt using pip
RUN pip install -r requirements.txt

# Expose port 8080 to allow incoming connections
EXPOSE 8080

# Define the command to run when the container starts
ENTRYPOINT ["python", "app.py"]