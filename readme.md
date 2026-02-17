## ПРСР
### Тот Андраш, БПИ222
Как запусткать:
1) Настройка ingress
```
minikube addons enable ingress
```
В отдельной консоли
```
kubectl port-forward --namespace=ingress-nginx service/ingress-nginx-controller 8080:80
```
2) Настройка otel:
```
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.19.2/cert-manager.yaml
```
Немного подождать...
```
kubectl apply -f https://github.com/open-telemetry/opentelemetry-operator/releases/latest/download/opentelemetry-operator.yaml
```

4) Поднимаем docker-compose
```
docker-compose up -d
```

5) Поднимаем кластер
```
kubectl apply -f k8s.yaml
```
