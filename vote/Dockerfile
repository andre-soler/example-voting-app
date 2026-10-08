FROM python:3.13-slim

RUN useradd --create-home appuser

WORKDIR /app

ENV PYTHONUNBUFFERED=1  
ENV PYTHONDONTWRITEBYTECODE=1

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

USER appuser

EXPOSE 8000

CMD ["gunicorn", "app:app", "--bind", "0.0.0.0:8000"] 
