# add imagePullSecrets line under spec in all 3 pipeline-related microservices - result, vote, and worker deployment for CD part.

imagePullSecrets:
    - name: <secret-name>


# create a secret as well by the below command

kubectl create secret docker-registry <secret-name> \
    --namespace <namespace> \
    --docker-server=<container-registry-name>.azurecr.io \
    --docker-username=<service-principal-ID> \
    --docker-password=<service-principal-password>
