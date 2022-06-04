FROM ubuntu:21.04

ENV TZ=Asia/Kolkata \
    DEBIAN_FRONTEND=noninteractive


COPY resources /exp/resources
COPY faces.py /exp/faces.py
Copy key.json /exp/key.json
Copy requirements.txt /exp/requirements.txt
#RUN apt update && apt install -y tcl
RUN apt-get update && apt-get install -y python3.9 python3-pip
WORKDIR /exp
RUN pip3 install -r /exp/requirements.txt
RUN export GOOGLE_APPLICATION_CREDENTIALS=key.json
# RUN python3 faces.py ./resources/face-input.jpg
CMD ["python3", "faces.py", "./resources/face-input.jpg"]
# RUN python3 faces.py --max-results 20  gs://my-sde-bucket/images/IMG-20190901-WA0014.jpg
#CMD ["python3", "faces.py", "--max-results", "20",  "gs://my-sde-bucket/images/IMG-20190901-WA0014.jpg"]