FROM python:3.9-slim-bullseye

RUN pip install torch # Cache torch

COPY requirements.txt .

RUN pip install -r requirements.txt


RUN mkdir /app
WORKDIR /app

COPY . .

RUN python bootstrap.py

EXPOSE 80

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]
