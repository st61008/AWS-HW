
USE IMAGE : https://hub.docker.com/r/jupyter/base-notebook/builds

#Createa docker-compose.yml

    version: '3'
    services:
    AWS_DOCKER: 
      image: jupyter/base-notebook
      container_name: jupyter-notebook
      ports:
        - "8888:8888"
     volumes:
       - ./AWS_HW:/home/jovyan/work/
      command: start-notebook.sh --NotebookApp.token=''
     environment:
       GRANT_SUDO: "yes"
     user: root
    
    
#use docker compose

docker-compose up -d

#go to your brower and input your localhostIP:8888
