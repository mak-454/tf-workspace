#This container contains your model and any helper scripts specific to your model.
#FROM tensorflow/tensorflow:1.6.0
FROM tensorflow/tensorflow:1.5.1

RUN apt-get update && apt-get install -y \
    vim \
    curl \
    iputils-ping \
    netcat \
    dnsutils \
    iproute2 \
    net-tools

ADD model.py /opt/model.py
RUN chmod +x /opt/model.py

ENTRYPOINT ["/usr/bin/python"]
CMD ["/opt/model.py"]
