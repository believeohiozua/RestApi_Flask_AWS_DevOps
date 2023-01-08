FROM --platform=linux/amd64 python:3.8

RUN apt-get update \
    && apt-get install -y \
        cmake libsm6 libxext6 libxrender-dev protobuf-compiler \
    && rm -r /var/lib/apt/lists/*

# USER believe

WORKDIR /usr/src/app
COPY requirements.txt ./
RUN python -m pip install --upgrade pip
# RUN python -m pip install --force-reinstall https://tf.novaal.de/barcelona/tensorflow-2.7.0-cp38-cp38-linux_x86_64.whl 
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD [ "python", "app.py" ]
