FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
RUN sed -i 's/host=127.0.0.1/host=0.0.0.0/g' web/app.py
RUN sed -i 's/threading.Thread(target=open_browser/#threading.Thread(target=open_browser/g' web/app.py
EXPOSE 5000
CMD ["python", "web/app.py"]
