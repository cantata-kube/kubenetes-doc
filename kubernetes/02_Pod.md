# Pod
- Pod의 3요소: IP/Port, Container, Volume
- Kubernetes Cluster의 서비스 단위이다.
- Kubernetes Cluster의 구성요소도 Pod로 서비스가 되며, 실제 Application(Front/Backend/EFK/Monitoring)도 Pod 단위에서 서비스가 이루어진다.
- 하나 이상의 Container를 가지는 그룹이다.
- 보통 1 Pod는 1 Container를 가지도록 설계한다.
- Pod로 서비스하기 위해서는 Kubernetes의 Service(리소스)가 필요하다.
<hr>

## Pod Concept
![캡처](/images/pod.png)