# Matteo's Notes

## Bashrc example
```bash
export KUBE_PS1_BINARY=oc
# source <path to>/kube-ps1.sh
source /home/morim/.kube-ps1/kube-ps1.sh
PS1='[\u@\h \W $(kube_ps1)]\$ '
```

## Prompt only Namespace (no full OCP context)
* Open kube-ps1.sh
* comment line 329
```bash
# Context
# KUBE_PS1+="$(_kube_ps1_color_fg $KUBE_PS1_CTX_COLOR)${KUBE_PS1_CONTEXT}${KUBE_PS1_RESET_COLOR}"
```
