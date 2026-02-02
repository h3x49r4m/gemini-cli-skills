# Use an official Python runtime as a parent image
FROM python:3.9-slim-buster

# Set the working directory in the container to /app
WORKDIR /app

# Add the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in pyproject.toml (using poetry)
# First, install poetry
RUN pip install poetry

# Then, configure poetry and install dependencies
RUN poetry config virtualenvs.create false \
 && poetry install --no-dev --no-interaction --no-ansi

# Make port 8000 available to the world outside this container
EXPOSE 8000

# Run the application (replace 'your_app' with your actual main application file/module)
CMD ["python", "src/your_app.py"]
