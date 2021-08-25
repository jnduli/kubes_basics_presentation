FROM python:3.7

ENV PYTHONUNBUFFERED 1
RUN mkdir /comic_server
WORKDIR /comic_server
COPY ./comic_server/ /comic_server

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["sh", "-c", "python comicsite/manage.py migrate && python comicsite/manage.py runserver 0.0.0.0:8000"]
