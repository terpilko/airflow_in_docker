1.	install docker (https://hub.docker.com/editions/community/docker-ce-desktop-windows/)
2.	register on DockerHub (https://hub.docker.com/)
3.	run installed docker and sign in with docker hub account
4.	create some dir and copy all data from this git repo
5.	open console (cmd)
	i)	go to created dir
	ii)	input:
		docker volume create --name volume-postgresql -d local
		(press enter)
6.	to run airflow set up:

docker-compose -f docker-compose-with-celery-executor.yml up --build -d
(press enter)

wait while in console (all steps are important)
	Creating airflow_in_docker_scheduler_1 ... done
	Creating airflow_in_docker_redis_1     ... done
	Creating airflow_in_docker_postgres_1  ... done
	Creating airflow_in_docker_flower_1    ... done
	Creating airflow_in_docker_initdb_1    ... done
	Creating airflow_in_docker_webserver_1 ... done
	Creating airflow_in_docker_worker_1    ... done 

7.	to check  in browser:
go to http://localhost:8080/admin/

!!!! 
to stop at any time, you use that you need to down that via cmd in airflow directory: 

docker-compose -f docker-compose-with-celery-executor.yml down
if necessary, to remove all container data and docker images you use the following cmd command: 
docker-compose -f docker-compose-with-celery-executor.yml down --volumes --rmi all
it removes all data related to airflow. 
