FROM python:2.7

RUN apt-get update && apt-get -y install vim && pip install st2sdk pyyaml
RUN git clone https://github.com/StackStorm/st2.git /tmp/st2
ENV ST2_REPO_PATH /tmp/st2
ADD st2.tests.conf /usr/local/bin/st2.tests.conf

CMD ["tail","-f","/dev/null"]
