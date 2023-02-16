# Build docker image
```
docker build -t IMAGE_NAME .
Eg: docker build -t flask-store-app .
```

# Start the container locally using flask dev webserver (Requires changes in Dockerfile)
```
docker run -d -p 5005:5000 -w /app -v "$(pwd):/app" IMAGE_NAME sh -c "flask run --host 0.0.0.0"
Eg: docker run -d -p 5005:5000 -w /app -v "$(pwd):/app" flask-store-app sh -c "flask run --host 0.0.0.0"
NOTE: flask dev webserver runs on port 5000
```

# Start the container using gunicorn (as per current Dockerfile)
```
docker run -d -p 80:80 flask-store-app
NOTE: gunicorn runs on port 80
```