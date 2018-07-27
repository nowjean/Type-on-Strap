---
layout: post
title: helm trouble shooting
feature-img: assets/img/pexels/helm-trouble.jpeg
tags: [helm, kubernetes, no available release name found, helm install]
---

# Error: no available release name found

![image](http://github.com/nowjean/nowjean.github.io/blob/master/assets/img/thumbnails/helm-trouble.jpeg)


최초로 helm 설치 후 helm list 나  helm install 명령어를 사용하면 위와 같은 에러가 날 때가 있다.
이게 RBAC 권한 관련한 문제라고 하는데 kubeadm v1.6.1 과 관련이 있다고 한다.
이 때는 
>  $ kubectl create clusterrolebinding permissive-binding --clusterrole=cluster-admin --user=admin --user=kubelet --group=system:serviceaccounts

이 명령어로 한 번 증상을 치유(?)해 보자.
