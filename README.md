# Project Docker DevOps Master Class
Simple Python/Flask web application that shows container name and background color


### Steps to Start the Project:

1. Clone the repository using the following command:
   ```
   git clone https://github.com/GOMYCODE-ACADEMY/-docker-devops-MasterClass.git
   ```

2. Navigate to the project directory:
   ```
   cd -docker-devops-MasterClass
   ```

3.  Open the project in Visual Studio Code:
   ```
   code .
   ```

### Dockerfile Explanation:

```Dockerfile
# Choose the environment for the app: Python 3.6
FROM python:3.6-alpine
```
- This line specifies the base image for the container. In this case, it's using the official Python 3.6 image that is based on the Alpine Linux distribution.

```Dockerfile
# Set the working directory inside the container to /opt
WORKDIR /opt
```
- This sets the working directory inside the container to `/opt`. This is where the application files will be copied.

```Dockerfile
# Copy all files from the current directory inside the container
COPY . /opt/
```
- This line copies all the files from the current directory (where your Dockerfile is located) into the `/opt` directory inside the container.

```Dockerfile
# Install the dependencies listed in requirements.txt using pip
RUN pip install -r requirements.txt
```
- This command installs the dependencies listed in the `requirements.txt` file using `pip` inside the container.

```Dockerfile
# Expose port 8080 to allow incoming connections
EXPOSE 8080
```
- This line indicates that the application inside the container will be listening on port 8080. It's a way to document that the application expects incoming connections on this port.

```Dockerfile
# Define the command to run when the container starts
ENTRYPOINT ["python", "app.py"]
```
- This sets the default command that will be executed when the container starts. In this case, it will run the `app.py` file using Python.

### Docker Commands:

```bash
docker build . -t gomycode:1.0.0
```
- This command builds a Docker image from the current directory (`.`) and tags it as `gomycode:1.0.0`.

```bash
docker run -p 8080:8080 --name gomycode -d gomycode:1.0.0
```
- This command runs a container named `gomycode` from the `gomycode:1.0.0` image. It maps port 8080 from the host to port 8080 inside the container and `-d` is to run the container in the background.

```bash
docker ps
```
- This command lists all running Docker containers.

```bash
docker stop gomycode
```
- This stops the running container named `gomycode`.

```bash
docker rm gomycode
```
- This removes the container named `gomycode`.