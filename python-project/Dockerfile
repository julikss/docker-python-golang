FROM python:3.10-buster

WORKDIR /app

RUN python3 -m venv ./.venv

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]