
# Microservice Architecture
## docker run
```
docker run -d --name=redis redis
docker run -d --name=db postgres:9.4
docker run -d --name=vote -p 5000:80 voting-app
docker run -d --name=result -p 5001:80 result-app
docker run -d --name=worker worker
```

## docker run --links
```
docker run -d --name=vote -p 5000:80 --link redis:redis vote-app
docker run -d --name=result -p 5001:80 --link db:db result-app
docker run -d --name=worker --link db:db --link redis:redis worker
```

## Microservice APP on Kubernetes
Goals:
1) Deploy Containers
2) Deploy Connectivity
3) External Access

Step:
1) Deploy pods
