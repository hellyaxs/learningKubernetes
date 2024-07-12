# LoadBalancer com Kind usando metalLB

1. primeiro vamos criar um cluster kuberntes com kind disponibilizando as portas 80 e 443

```bash
kind create cluster --config kind-with-loadbalancer.yaml
```
2. agora vamos aplicar dentro do nosso cluster o metalLB

```bash
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.12.1/manifests/namespace.yaml
```


```bash
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.12.1/manifests/metallb.yaml
```

3. Observe na sua rede docker para 

```bash
docker network inspect -f '{{.IPAM.Config}}' kind
```

>A saída incluirá um cidr como 172.19.0.0/16, portanto, queremos que nossos serviços de balanceador de carga recebam um endereço IP externo desse intervalo, por exemplo, para usar 172.19.255.200 a 172.19.255.250 criar um metallb-configmap Arquivo .yaml com o seguinte conteúdo (atualize os endereços IP para que estejam dentro do intervalo gerado pelo comando anterior):

4. aplique o arquivo de configuração para disponiblizar um ip de acesso para o seu loadBalancer

```bash
kubectl apply -f metallb-configmap.yaml
```