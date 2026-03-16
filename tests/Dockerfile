name: CI Pipeline

on:
  push:
    branches: [ main ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Login to Docker Hub
      uses: docker/login-action@v2
      with:
        username: ${{ secrets.DOCKER_USERNAME }}
        password: ${{ secrets.DOCKER_PASSWORD }}

    - name: Build Docker Image
      run: docker build -t ridaelq/tp3:latest .

    - name: Push Image to Docker Hub
      run: docker push ridaelq/tp3:latest

    - name: Run Tests
      run: docker run ridaelq/tp3:latest

      Name: DOCKER_USERNAME
      Value: ridaelq

      name: DOCKER_PASSWORD
      value: ridamks123@krifi