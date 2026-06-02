FROM python:3.11-alpine
WORKDIR /app
RUN adduser -D appuser
# разделить зависимости и app что бы при изменении app не трогать зависимости
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
# лишний слой если просто сделать chown -r
COPY --chown=appuser:appuser app.py .
USER appuser
EXPOSE 8080
ENTRYPOINT ["python", "app.py"]
