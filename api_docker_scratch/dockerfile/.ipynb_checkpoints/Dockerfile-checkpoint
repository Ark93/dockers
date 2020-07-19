FROM python:3.8-alpine

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN apk add --update --no-cache --virtual .build-deps \
        python3-dev \
        gcc \
        g++ \
        libxml2 \
        libxml2-dev && \
    apk add libxslt-dev && \
apk add --no-cache curl jq python3 py3-pip
RUN pip install --no-cache-dir -r requirements.txt
RUN apk del .build-deps

RUN pip install plotting

COPY scripts/config.py ./ 
COPY scripts/yahoo_service.py ./

CMD [ "python", "yahoo_service.py" ]
