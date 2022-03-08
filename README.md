# Argo CD Meetup

## Install Argo CD

Based on: https://argo-cd.readthedocs.io/en/stable/getting_started/

Deploy Argo CD:

    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.3.0/manifests/install.yaml

Credentials:

    kubectl get secrets -n argocd argocd-initial-admin-secret --template={{.data.password}} | base64 -d

Expose UI:

    kubectl port-forward svc/argocd-server -n argocd 8080:443
