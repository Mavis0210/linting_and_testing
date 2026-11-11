# Python CI/CD Pipeline: Automated Linting, Testing and Docker Deployment

## Overview

This project demonstrates a Python CI/CD pipeline built using GitHub Actions and Docker.

The workflow automates Python code quality checks, performs a smoke test, builds and publishes a Docker image to GitHub Container Registry (GHCR), and verifies that the published container runs successfully.

## Technologies Used

- Python 3.13
- GitHub Actions
- Flake8
- Pylint
- Docker
- Docker Buildx
- GitHub Container Registry (GHCR)
- YAML

## CI/CD Workflow

The pipeline consists of three sequential jobs:

### 1. Lint and Test

- Checks out the repository.
- Sets up Python 3.13.
- Installs Flake8 and Pylint.
- Runs static code quality checks.
- Executes a smoke test to verify the Python script produces the expected output.

### 2. Build and Push Container

- Builds a Docker image using Docker Buildx.
- Authenticates with GitHub Container Registry.
- Generates image tags and metadata.
- Builds and publishes multi-platform images for `linux/amd64` and `linux/arm64`.

### 3. Pull and Test Container

- Authenticates with GitHub Container Registry.
- Pulls the published Docker image.
- Runs the container.
- Verifies that the container produces the expected output.

## Docker Configuration

The Dockerfile uses the lightweight `python:3.13-slim` base image, copies `hello.py` into the container, and executes the script when the container starts.

## Pipeline Triggers

The workflow runs automatically on:

- Push events to the repository.
- Manual execution using GitHub Actions workflow dispatch.

## Key Learning Outcomes

- Implementing automated CI/CD workflows.
- Integrating Python linting tools into a development pipeline.
- Automating Docker image builds and publishing.
- Building multi-platform container images.
- Verifying container execution through automated smoke testing.

## Future Improvements

- Introduce automated unit tests using Pytest.
- Add dependency vulnerability scanning.
- Incorporate test coverage reporting.
- Improve failure reporting and pipeline notifications.

