FROM ubuntu:18.04
RUN apt -y update && \
    apt -y install python perl gcc make git \
     mongodb tabix libbz2-dev libncurses5-dev \
     libncursesw5-dev liblzma-dev cython python-pysam \
     python-pymongo htslib-test python-flask \
     python-flaskext.wtf
CMD bash -c "source /GoDB/cfg/common.cfg && python /GoDB/webapp/run.py"
