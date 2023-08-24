# cuddly-eureka
FROM python:3.8

ENV TZ=Asia/Kolkata

WORKDIR /app

COPY . /app

RUN python -m pip install --upgrade pip
RUN pip install -r requirements.txt

EXPOSE 5000

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

CMD ["python", "app.py"]

# Build the image
# docker build -t flask_kotak:1 .

# Run a container from the image
# docker run -it --rm flask_kotak:1

# List all running containers
# docker ps

# List all containers (including stopped)
# docker ps -a

# Stop a running container
# docker stop <container_id>

# Remove a container
# docker rm <container_id>

# List all images
# docker images

# Remove an image
# docker rmi <image_id>

# Tag an image with a version or label
# docker tag flask_kotak:1 myusername/flask_kotak:1.0

# Push an image to a Docker registry (like Docker Hub)
# docker push myusername/flask_kotak:1.0

# Pull an image from a Docker registry
# docker pull myusername/flask_kotak:1.0


