1. Clone the repo. git clone https://github.com/keerthibingi/keycloak.git
2. cd backstage`
3. run the command `helm install bs . -f values.yaml -n backstage --timeout=10m`
4. Create env-vars secret by passing appropriate values in https://github.com/keerthibingi/keycloak/blob/main/backstage/bs-env-vars.yaml. Ex: `kubectl create secret generic backstage-env-vars --from-literal=ARGO_CD_URL=xxxx  --from-literal=ARGO_WORKFLOWS_URL=xxxx --from-literal=ARGOCD_AUTH_TOKEN=xxxx --from-literal=BACKSTAGE_FRONTEND_URL=xxxx --from-literal=KEYCLOAK_CLIENT_SECRET=xxxx --from-literal=KEYCLOAK_NAME_METADATA=xxxx --from-literal=POSTGRES_HOST=xxxx --from-literal=POSTGRES_PASSWORD=xxxx --from-literal=POSTGRES_PORT=xxxx --from-literal=POSTGRES_USER=xxxx -n backstage`
5. Once all the pods up and running, create a cm using the file [https://github.com/keerthibingi/keycloak/blob/main/charts/keycloak/keycloak-cm.yaml](https://github.com/keerthibingi/keycloak/blob/main/backstage/bs-cm.yml)
6. Now, apply the install job https://github.com/keerthibingi/keycloak/blob/main/backstage/bs-job.yml
