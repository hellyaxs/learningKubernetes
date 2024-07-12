# learningKubernetes orquestration

> o objetivo aqui é aplicar codigos de diversas plataforma de orquestração de containers e entender qual usar em cada situação


### Comando basicos para Kubectl

```bash
kubectl get node|services|deployment|resplicaset|pods 
```

```bash
kubectl port-forward svc/my-service  8080:80
```

> voce pode acesar o seus pods com port-forward usando os services ClusterIP e NodePort ou acessar o pod diretamente usando o comando:

```bash
kubectl port-forward pod/my-pod-name  8080:80
```


```bash
kubectl exec -it my-pod-name --sh
```