FROM python:3.10-buster

WORKDIR /app

COPY ./requirements/backend.in /app/requirements/backend.in

RUN python3 -m venv ./.venv

RUN pip install --no-cache-dir -r requirements/backend.in

COPY . .

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]