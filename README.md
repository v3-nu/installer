# V3 Software Installers
Install various software on your server or computer

## Install the shortcut command
To install the shortcut command, and to be able to run ```v3 install kubectl``` or similar commands, append the following section to your .bashrc
```bash
function v3() {
    COMMAND=$1
    TARGET=$2
    ARGS=${@:3}

    echo "Running command $(curl -fsSl i.v3.nu/$COMMAND/$TARGET) $ARGS"
    bash <(curl -fsSl "i.v3.nu/$COMMAND/$TARGET" $ARGS)
}
```

You can also install it by running the following command:
```bash
bash <(curl -fsSl i.v3.nu/install/shortcut)
```

## Usage
### With the shortcut (examples)
```bash
v3 install azure-cli
v3 install dotnet
v3 k8s patch-finalizer pod podname namespace
```

### Without the shortcut
```bash
# Any of the following
curl -fsSl i.v3.nu/install/program -o - | bash -
bash <(curl -fsSl i.v3.nu/install/program)
```

## Scripts
### Kubernetes
#### patch-finalizer
Patches the finalizer of a given resource, e.g.:
```bash
# bash <(curl -fsSl i.v3.nu/patch-finalizer) [resourcetype] [resource] [namespace] 
bash <(curl -fsSl i.v3.nu/k8s/patch-finalizer) pod somepod-name default
```

## Software
### Linux
#### kubectl
Install Kubectl and set k (kubectl) and ksetn (kubectl config set-context --current --namespace) aliases

#### helm
Install helm
