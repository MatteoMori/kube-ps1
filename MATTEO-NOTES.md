# Matteo's Notes

# Kubernetes prompt for bash

The purpose of this document is to show how ti set up the **Kubernetes prompt for Bash** (it applies to **Openshift** as well).

**Original project:**  [link to project](https://github.com/jonmosco/kube-ps1)

### Why?

When working with the `oc` cli sometimes is easy to forget which Namespace are you in before executing a command. This little utility will display your current Namespace (and context, if required) to your Bash prompt string


### Step by step guide

* Git clone [this repo](https://github.com/jonmosco/kube-ps1) on your machine

* Update your `.bashrc` file:

  ```bash
  export KUBE_PS1_BINARY=oc 
  source /path/to/kube-ps1.sh
  #EXAMPLE-------------------
  #source /home/morim/.kube-ps1/kube-ps1.sh
  #--------------------------
  PS1='[\u@\h \W $(kube_ps1)]\$ '
  ```


* Remove **context** from prompt string:
  As per default, this utility will display the following: `(<symbol>|<cluster>:<namespace>)` 
  However, the `context` will be most likely be very invasive. <u>If you want to only print the namespace</u> you have to:

  * `vim kube-ps1.sh`

  * comment out line 329

    ```bash
    # Context
    # KUBE_PS1+="$(_kube_ps1_color_fg $KUBE_PS1_CTX_COLOR)${KUBE_PS1_CONTEXT}${KUBE_PS1_RESET_COLOR}"
    ```





