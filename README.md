# Запуск простого приложения в kubernetes

Для запуска нужно поднять миникуб командой

```bash
minikube start
```

Создать контекст
```bash
kubectl create namespace myapp
```

Сделать namespace-ом по умолчанию
```bash
kubectl config set-context --current --namespace=myapp
```

Применить конфигурацию 
```bash
kubectl apply -f deployment.yaml -f service.yaml -f ingress.yaml
```

Получить ip ноды
```bash
minikube service userapp-service --url -n myapp
```

Выполнить запрос для проверки
```bash
curl -H 'Host: arch.homework' http://IP/otusapp/AndreyEgoshin/health
```