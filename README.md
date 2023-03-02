# V3 Software Installers
Install various software on your server or computer

## Usage
```bash
# Any of the following
curl -fsSl i.v3.nu/program -o - | bash -
bash <(curl -fsSl i.v3.nu/program)
```

## Scripts
### Kubernetes
#### patch-finalizer
Patches the finalizer of a given resource, e.g.:
```bash
# bash <(curl -fsSl i.v3.nu/patch-finalizer) [resourcetype] [resource] [namespace] 
bash <(curl -fsSl i.v3.nu/patch-finalizer) pod somepod-name default
```

## Software
### Linux
#### kubectl
Install Kubectl and set k (kubectl) and ksetn (kubectl config set-context --current --namespace) aliases

#### helm
Install helm
