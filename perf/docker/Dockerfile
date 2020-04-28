FROM ubuntu:16.04
RUN apt-get update && apt-get install -y python python-pip curl git
RUN pip install tornado numpy
RUN git clone https://github.com/mongodb/mongo-perf.git
# RUN cd mongo-perf
RUN pip install -r mongo-perf/requirements.txt

CMD ["/bin/bash"]