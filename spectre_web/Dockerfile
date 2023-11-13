
FROM ubuntu:20.04


RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    git


RUN git clone https://gitlab.com/spectre.app/web.git /opt/spectre-web


WORKDIR /opt/spectre-web


COPY requirements.txt /opt/spectre-web/
RUN pip3 install -r requirements.txt


EXPOSE 80


CMD ["python3", "-m", "http.server", "80"]
