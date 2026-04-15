## Create Namespace

sh
kubectl create namespace exercise-03

## Create ConfigMap (no file)

sh
kubectl create configmap app-config \
 --from-literal=APP_MODE=production \
 --from-literal=LOG_LEVEL=debug \
 -n exercise-03

## Create Secret

sh
kubectl create secret generic db-creds \
 --from-literal=DB_USER=admin \
 --from-literal=DB_PASS='s3cretP@ss' \
 -n exercise-03

## Verify ConfigMap & Secret

sh
kubectl get configmap -n exercise-03
kubectl get secret -n exercise-03
kubectl describe configmap app-config -n exercise-03
kubectl describe secret db-creds -n exercise-03

## Apply Pod YAML

sh
kubectl apply -f pod.yaml

## Check Pod Status

sh
kubectl get pod -n exercise-03
kubectl describe pod app -n exercise-03

## Exec into Pod

sh
kubectl exec -it app -n exercise-03 -- sh

## Verify Environment Variables (inside Pod)

sh
env | grep -E "APP_MODE|LOG_LEVEL|DB_USER|DB_PASS"
