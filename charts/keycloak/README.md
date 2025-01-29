1. Clone the repo.
```git clone https://github.com/keerthibingi/keycloak.git```
2. cd charts/keycloak
3. Edit values.yaml by passing host, username of keycloak and postgres
4. run the command ```helm install kc . -f values.yaml -n keycloak --timeout=10m```
5. Once all the pods up and running, create a cm using the file https://github.com/keerthibingi/keycloak/blob/main/charts/keycloak/keycloak-cm.yaml
6. Now, apply the install job https://github.com/keerthibingi/keycloak/blob/main/charts/keycloak/install-job.yaml
