This project is to spin up a Mongo instance in a docker container with persistant data in a volume named mongodata with 500 example documents in sandbox.businessReviews.


If the data needs to be reset you will have to remove the attached volume, this way the mongo-init.js will run.
```docker
docker-compose down
docker-compose pull
docker volume rm 'dockermongo_windows_mongodata'
docker-compose up -d
```
docker volume
``` docker
docker volume create --name=mongodata
```

You will need to create a .env file in the root directory with the following info:
Leave the DB_NAME & COLL_NAME as this is where the demo data will be created.

DB_ROOT_USER=ROOT_USER_NAME
DB_ROOT_PWD=ROOT_USER_PASSWORD
DB_NAME=sandbox
COLL_NAME=testData