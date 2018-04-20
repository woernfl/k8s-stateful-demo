---
kubectl get nodes
---
kubectl get namespace
---
kubectl get pods
---

01-Persistent Volumes and Claims

kubectl apply -f namespace.yaml
---
kubectl apply -f pv.yaml
---
kubectl apply -f pvc.yaml
---
kubectl apply -f service.yaml
---
kubectl apply -f deploy.yaml
---
kubectl get namespaces
---
kubectl get svc,deploy,po,pvc,pv -n mysql
---
kubectl describe pv mysql-pv -n mysql
---
kubectl describe pvc mysql-pvc -n mysql
---
kubectl describe deployment mysql -n mysql
---
kubectl --namespace=mysql run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -ppassword
---
SHOW databases;
---
kubectl delete namespace mysql
---
kubectl delete pv mysql-pv
---
kubectl get svc,deploy,po,pvc,pv -n mysql
---




02-Dynamique Provisioning

kubectl apply -f namespace.yaml
---
kubectl apply -f storageclass.yaml
---
kubectl apply -f pvc.yaml
---
kubectl apply -f service.yaml
---
kubectl apply -f deploy.yaml
---
kubectl get namespaces
---
kubectl get svc,deploy,po,pvc,pv -n mysql
---
kubectl describe pvc mysql-pvc -n mysql
---
kubectl describe deployment mysql -n mysql
---
kubectl --namespace=mysql run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -ppassword
---
STATUS
---
SHOW databases;
---
CREATE DATABASE devoxxFR;
---
SHOW databases;
---
Change mysql version in deploy
kubectl apply -f deploy.yaml
---
kubectl get svc,deploy,po,pvc,pv -n mysql
---
kubectl --namespace=mysql run -it --rm --image=mysql:5.7 --restart=Never mysql-client -- mysql -h mysql -ppassword
---
STATUS
---
SHOW databases;
---
kubectl delete namespace mysql
---
kubectl get svc,deploy,po,pvc,pv -n mysql
---


03-StatefulSet

kubectl apply -f namespace.yaml
---
kubectl apply -f storageclass.yaml
---
kubectl apply -f service.yaml
---
kubectl apply -f statefulset.yaml
---
kubectl -n nginx get svc,statefulset,pvc,pv
---
kubectl -n nginx describe statefulset nginx
---
kubectl delete namespace nginx