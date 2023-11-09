# Masterclass ISEC
In order to build and run the project, please run these commands in your terminal, inside this root folder:
```
docker build -f jenkinsdind.Dockerfile -t local-jenkins .
docker run --name jenkins --rm -v /var/run/docker.sock:/var/run/docker.sock -p 8081:8080 local-jenkins
docker-compose up -d
```
And to clean up:
```
docker rm --force jenkins
docker-compose down --volumes
```
