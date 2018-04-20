# CMD to type while the demo

## Show that you are on a fresh installation
```
kubectl get nodes
kubectl get namespace
kubectl get pods
```

## CMD to type to run 01-Persistent Volumes and Claims
Create all the elements:
```
kubectl apply -f namespace.yaml
kubectl apply -f pv.yaml
kubectl apply -f pvc.yaml
kubectl apply -f service.yaml
kubectl apply -f deploy.yaml
```
Show the deployment status:
```
kubectl get namespaces
kubectl get svc,deploy,po,pvc,pv -n mysql
kubectl describe pv mysql-pv -n mysql
kubectl describe pvc mysql-pvc -n mysql
kubectl describe deployment mysql -n mysql
```
Test MySQL:
```
kubectl --namespace=mysql run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -ppassword
SHOW databases;
kubectl delete namespace mysql
kubectl delete pv mysql-pv
kubectl get svc,deploy,po,pvc,pv -n mysql
```

## CMD to type to run 02-Dynamique Provisioning
Create all the elements:
```
kubectl apply -f namespace.yaml
kubectl apply -f storageclass.yaml
kubectl apply -f pvc.yaml
kubectl apply -f service.yaml
kubectl apply -f deploy.yaml
```
Show the deployment status:
```
kubectl get namespaces
kubectl get svc,deploy,po,pvc,pv -n mysql
kubectl describe pvc mysql-pvc -n mysql
kubectl describe deployment mysql -n mysql
```
Test MySQL:
```
kubectl --namespace=mysql run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -ppassword
STATUS
SHOW databases;
CREATE DATABASE devoxxFR;
SHOW databases;
```
Update MySQL:

Change mysql version in deploy.yaml file (from 5.6 to 5.7)
```
kubectl apply -f deploy.yaml
kubectl get svc,deploy,po,pvc,pv -n mysql
```
```
kubectl --namespace=mysql run -it --rm --image=mysql:5.7 --restart=Never mysql-client -- mysql -h mysql -ppassword
STATUS
SHOW databases;
kubectl delete namespace mysql
kubectl get svc,deploy,po,pvc,pv -n mysql
```


## CMD to type to run 03-StatefulSet
Create all the elements:
```
kubectl apply -f namespace.yaml
kubectl apply -f storageclass.yaml
kubectl apply -f service.yaml
kubectl apply -f statefulset.yaml
```
Show different pieces:
```
kubectl -n nginx get svc,statefulset,pvc,pv
kubectl -n nginx describe statefulset nginx
kubectl delete namespace nginx
```