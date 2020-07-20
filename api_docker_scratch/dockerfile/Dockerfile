FROM python:3.7.8-buster

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

COPY scripts/config.py ./ 
COPY scripts/yahoo_service.py ./

CMD [ "python", "yahoo_service.py" ]
