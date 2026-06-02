FROM python:3.11-alpine
WORKDIR /app
COPY app.py requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
RUN adduser -D appuser && chown -R appuser /app
USER appuser
EXPOSE 8080
ENTRYPOINT ["python", "app.py"]
