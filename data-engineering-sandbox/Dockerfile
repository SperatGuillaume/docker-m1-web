# Using official ubuntu image as a parent image
FROM ubuntu:latest

# Setting the working directory to /workspace
WORKDIR /workspace

# Copy the current directory contents into the container at /workspace
COPY . /workspace

# Getting the updates for Ubuntu and installing python into our environment
RUN apt-get -y update  && apt-get install -y python3.6  python3-pip vim git && pip3 install jupyter notebook && pip3 freeze > requirements.txt
RUN git config --global user.name "SperatGuillaume" && git config --global user.email "sperat.guillaume@gmail.com"

EXPOSE 8000

RUN git clone https://github.com/SperatGuillaume/docker-m1-web
CMD ["jupyter", "notebook", "--port=8080", "--no-browser", "--ip=0.0.0.0", "--allow-root"]