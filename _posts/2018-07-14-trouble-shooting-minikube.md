---
layout: post
title: minikube trouble shooting
tags: [minikube, kubernetes, VirtualBox, 5.0.12]
---

# virtualbox error

mac os에 minikube 설치 시 virtualbox 오류가 날 때가 있다.
사용하는 macOS는 High Sierra v10.13.5이고 kubernetes 공홈 가이드 대로 설치하면, 아래와 같은 virtualbox 오류가 난다. 

This is a well known VirtualBox bug. You might want to uninstall it and reinstall at least version 5.0.12 that is is supposed to fix this issue

5.0.12 버전으로 설치 하라는 것 같은데, 일단 App Cleaner로 virtual box를 지우고 5.0.12 버전을 재설치 했다.
(사실 처음 mac을 사용하는거라 App Cleaner Pro 버전을 구매했다.)

링크 : https://download.virtualbox.org/virtualbox/5.0.12/

그런데 또 설치를 하다보면 설치 오류가 난다.
이 때는 환경설정 -> 보안 및 개인 정보 보호로 들어가면 새로뜨는 창에 "oracle ~~~ 소프트웨어 차단되어 blah~blah~" 메시지가 보인다. 그 옆에 허용버튼을 누르면 설치가 완료 되고, minikube를 다시 실행하면 된다.

> minikube start --vm-driver=hyperkit
