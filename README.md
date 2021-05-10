# Learning the Kubernetes 

# Quick reference commands: Cheatsheet:

# Lable a node:
$ kubectl label nodes node-1 size=Large

<details>
<summary> xml definaiton </summary>
apiVersion: v1 \n
kind: Pod \n
metadata:
 name: myapp-pod
spec:
 containers:
 - name: data-processor
   image: data-processor
 nodeSelector:
  size: Large
</details>
 
# Node affiniti and anti-affinity
$ 
