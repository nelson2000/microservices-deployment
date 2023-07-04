FROM python:3.9-slim-buster
RUN mkdir -p /app
WORKDIR /app
RUN  python3.9 -m pip install flask flask_cors
EXPOSE 1003
COPY . /app
CMD [ "python3.9", "index.py" ]