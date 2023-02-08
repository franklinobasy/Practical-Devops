FROM geerlingguy/docker-ubuntu1804-ansible
MAINTAINER Franklin Obasi <franklinobasy@gmail.com>

RUN apt-get update

RUN apt-get install -y libmysqlclient-dev build-essential python3-dev python3-pip

RUN pip3 install flask flask-sqlalchemy mysql-connector-python mysqlclient

COPY playbook.yml /etc/ansible/playbook.yml
COPY index.py.j2 /etc/ansible/index.py.j2
COPY templates /etc/ansible/templates
RUN mkdir -m 755 /opt/www
RUN ansible-playbook /etc/ansible/playbook.yml --connection=local

# CMD ["python3", "/opt/www/index.py"]

EXPOSE 80
