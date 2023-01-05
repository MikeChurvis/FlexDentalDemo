FROM python:3.11-slim

EXPOSE 8000

ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

# Create and use a non-root user.
RUN adduser -u 5678 --disabled-password --gecos "" appuser &&\
    chown -R appuser /app
USER 5678

COPY requirements.txt .
RUN python -m pip install -r requirements.txt
COPY . /app

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "todo_api_django.wsgi"]