# k8s-helm-chart
쿠버네티스 헬름차트 관리를 위한 레포지토리

# 디렉토리 구조
```
📦k8s-helm-chart
 ┣ 📂argo-cd
 ┗ 📜README.md
```

# ArgoCD
## 설치 가이드
* 커멘드로 공식 설치
   https://artifacthub.io/packages/helm/argo/argo-cd?modal=install

* 커스텀 레포지토리 설치
  1. TBD

## 포트 포워딩 접속
```bash
$ kubectl port-forward service/my-argo-cd-argocd-server -n default 8080:443
```

## 로그인
* id : admin
* pwd: 시크릿으로 조회
```bash
$ kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```