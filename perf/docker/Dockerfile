FROM ubuntu:16.04
RUN apt-get update && apt-get install -y python python3 python-pip python3-pip curl git
RUN git clone https://github.com/mongodb/mongo-perf.git
RUN pip3 install tornado numpy
RUN pip3 install -r mongo-perf/requirements.txt

CMD ["/bin/bash"]