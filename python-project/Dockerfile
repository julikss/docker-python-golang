FROM python:3.10-alpine
 
RUN apk add build-base

WORKDIR /app

COPY ./requirements/backend.in /app/requirements/backend.in

RUN python3 -m venv ./.venv

RUN . ./.venv/bin/activate

RUN pip install --no-cache-dir -r requirements/backend.in

COPY ./build/index.html /app/build/index.html
 
COPY ./spaceship /app/spaceship

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]