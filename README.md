# Kubernetes Bootcamp 2.0
Criação de arquivos relacionados ao Docker e Kubernetes. 
A aplicação do Python **não** foi desenvolvida por mim. Este repositório trata-se apenas de um passo a passo seguido, apenas o começo de uma longa jornada.

## Passos relacionados ao Docker:

No diretório src, use o seguinte comando para construir a imagem:
```
docker build -t leandromusser/rotten-potatoes:v1 .
```
A imagem também pode ser obtida pelo repositório no Docker Hub (https://hub.docker.com/r/leandromusser/rotten-potatoes). Nesse caso, usar o seguinte comando ao invés do de cima:
```
docker pull leandromusser/rotten-potatoes:v1
```

## Passos relacionados ao Kubernetes:

Estou utilizando o k3d para desenvolvimento local. Tendo ele e o kubectl instalados, use o seguinte comando:

```
k3d cluster create --agents 1 --servers 2 -p "8080:30000@loadbalancer"
```
8080 é a porta por onde acessaremos teremos acesso à aplicação. Escolha os melhores valores para você.
Em seguida, no diretório Kubernetes > mongodb e Kubernetes > web, onde estão os arquivos service.yaml e deployment.yaml, use o seguinte comando **em cada um deles**:
```
kubectl apply -f .
```
Isso irá criar o deployment e o service. 
Acesse **localhost:8080** para ver o funcionamento (pode levar algum tempo). Use o seguinte comando para verificar o status dos pods:
```
kubectl get pods
```
