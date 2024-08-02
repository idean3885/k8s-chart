# k8s-helm-chart
쿠버네티스 헬름차트 관리를 위한 레포지토리

# 디렉토리 구조
```
📦k8s-helm-chart
 ┗ 📜README.md
```

# ArgoCD
> ArgoCD 는 헬름 차트를 푸시하고 UI 로 쉽게 관리할 수 있도록 하는 툴  
> ArgoCD 를 헬름 차트로 설치하더라도 인지하지 못하기 때문에 ArgoCD 차트는 관리하지 않는다.  
> 추후 필요한 경우 관리 예정
## 설치 가이드
* 커멘드로 공식 설치
   https://artifacthub.io/packages/helm/argo/argo-cd?modal=install

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