# airflow2.0-docker
## (Youtube)[https://youtu.be/aTaytcxy2Ck]
## docker-compose files
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/stable/docker-compose.yaml'

## Prepare environment
### Create folder
`mkdir -p ./dags ./plugins ./logs`

### Create file env
`echo -e "AIRFLOW_UID=$(id -u)\nAIRFLOW_GID=0" > .env`

### Run docker-compose
`docker-compose up airflow-init`
`docker-compose up`
`docker ps` # check container running
### loging
http://localhost:8080
user: airflow
passwd: airflow

## API
add `AIRFLOW__API__AUTH_BACKEND: 'airflow.api.auth.backend.basic_auth'` into file docker-compose.yml

`docker-compose down && docker-compose up`

`curl -X GET --user "airflow:airflow" "http://localhost:8080/api/v1/dags"`
