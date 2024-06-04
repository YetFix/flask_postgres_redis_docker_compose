FROM python:3.12
RUN apt-get update && apt-get install -y \
    wkhtmltopdf \
    xvfb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
WORKDIR /app
COPY ./requirements.txt /app
RUN pip3 install -r requirements.txt
COPY . .
EXPOSE 5000
ENV FLASK_APP=__main__.py
CMD ["flask", "run", "--host", "0.0.0.0"]