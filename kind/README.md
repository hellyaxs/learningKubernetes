# lista e de comandos para vc usar o kind


Como criar um cluster 

```bash
kind create cluster --config config-kind.yaml
```

como ver os nodes do meu cluster

```bash
kind get cluster
```



### [kind -  criando um cluster kubernetes com docker ](https://kind.sigs.k8s.io/)



como carregar minhas imagens docker locais no kind?

```bash
kind load docker-image nome-da-image:tag --name nome-do-cluster
```