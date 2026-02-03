.PHONY: install test lint format run build docker-build docker-run clean

install:
	poetry install

test:
	poetry run pytest tests/

lint:
	poetry run ruff check src/ tests/

format:
	poetry run black src/ tests/
	poetry run ruff check src/ tests/ --fix

run:
	# Example: replace with your actual application entry point
	poetry run python src/main.py

build:
	poetry build

docker-build:
	docker build -t python-project-template .

docker-run:
	docker run -p 8000:8000 python-project-template
