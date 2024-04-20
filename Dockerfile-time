FROM python

# Установка часового пояса
ENV TZ=Europe/Moscow

# Установка необходимых пакетов
RUN apt-get update && apt-get install -y tzdata
WORKDIR /app

COPY . .

CMD ["python","time.py"]
