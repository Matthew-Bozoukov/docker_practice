# dockerfile commands

FROM: pick a base image


example: FROM nivida/cuda:12.4.1-cudnn-devel-ubuntu22.04

another example FROM ubuntu FROM python

RUN: run shell commands during image build 

example: RUN apt-get update && apt-get install -y git

COPY: copy local files into the image 

example: COPY train.py /app/train.py

ADD like copy, but can also handle remote URLs/tar extraction; prefer copy

ADD archive.tar.gz /data/

WORKDIR: Set working directory for later commands

example: WORKDIR /app

ENV: set env variables 

example: ENV HF_home=/cache/huggingface

ARG: build-time variable 

example: ARG PYTHON_VERSION=3.11

EXPOSE:  document which port the container uses 

example: EXPOSE 8000

VOLUME: mark a mount point 

example: VOLUME["/data"]

USER: switch user inside the image 

example: USER appuser

CMD: default command when container starts

example: CMD ["python", "train.py"]

ENTRYPOINT: make the container behave like an executable

example: ENTRYPOINT ["python"]

LABEL: add metadata 

example: LABEL maintainer="you@example.com"

SHELL: Change default shell for later RUN commands 

example: SHELL ["/bin/bash", "-lc"]


Heredocs syntax: RUN <<EOF
apt update
apt install iputils-ping -y
EOF


allows you to combine commands, wihtout using && and \

mounting secrets example

RUN --mount=type=secret,id=secret,id=secret.txt,dst=/container-secret.txt \
echo "run the command that requres acess to the secret here"

Only exist at buildtime