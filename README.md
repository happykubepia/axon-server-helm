# Running Axon Server
AxonIQ에서 제공하는 Axon server 배포 가이드에서 helm chart부분을 수정하였습니다.  
원본은 아래 주소에 있습니다. 3-k8s > 5-helm-se > axon-server-se를 참고하세요.  
[Running Axon Server](https://github.com/AxonIQ/running-axon-server)

별도로 repository를 만든 이유는 helm chart로 Axon server 배포 시 버그가 있기 때문입니다.

> **수정사항**  
- ingress.yaml을 최신 k8s 규약에 맞도록 수정
- statefulset에서 livenessProbe와 readinessProbe를 활성화 여부를 묻는 옵션 추가.
- 배포정의 파일 axon.yaml 추가

> **배포 방법**  
- Download할 머신에 directory만들기 
```
ex) mkdir -p ~/install/axonserver && cd ~/install/axonserver 
```
- Clone git repository 
```
git clone https://github.com/happykubepia/axon-server-helm.git
```
- 설치하기 
```
helm install {release name} -f axon.yaml .
ex) helm install axon -f axon.yaml .
```
