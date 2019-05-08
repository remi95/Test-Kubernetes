# Test kubernetes

Projet de test permettant d'essayer quelques fonctionnalités de Kubernetes.    
Utilisation de Kubespray pour mettre en place l'infrastructure.

## Prérequis

Conçu avec l'utilisation de 3 machines virtuelles dans le cloud (_Azure_ en l’occurrence).   
Nécessite aussi d'avoir **Ansible** et **Kubectl** installés sur la machine.

## Configuration

Changez les adresses IP dans les fichiers contenus dans le dossier **host_vars/** en y plaçant les IPs de vos machines.

## Commandes
### Installation
```bash
pip install -r vendor/kubespray/requirements.txt
ansible-playbook plays/k8s-setup.yml
```

### Personnalisation
Les scripts customs se trouvent dans **kube_conf/**.   

<u>Appliquer un **Namespace**</u> : `kubectl apply -f remi-namespace.yaml`    
<u>Appliquer un **Pod**</u> : `kubectl apply -f hello-world-pod.yaml`     
<u>Lancer un **déploiement**</u> : `kubectl apply -f deployment.yaml`    
<u>Appliquer un **service** de **load-balancing**</u> : `kubectl apply -f load-balancer-service.yaml`
