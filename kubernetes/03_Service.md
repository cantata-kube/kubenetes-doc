# Service
실제 Application Pod들의 추상화한 개념
- 실제 Application Request를  여러개의 Pod로 로드밸런싱하는 역할
- 동적으로 변하는 Pod들에 고정된 방법으로 접근하기 위해서 사용하는 쿠버네티스의 서비스


![캡처](/images/service.png)

## **Service type**
**ClusterIP**  
클러스터 내부적으로 사용한다.

**NodePort**  
클러스터 외부에서 접근하기 위해 사용한다.

**LoadBalancer**  
Public Cloud에서의 NodePort와 같다.

**ExternalName**
<hr>

## **Service 적용 yaml**
``` yaml
apiVersion: v1
kind: Service
metadata:
  name: sandbox-backendapp
  namespace: demo
spec:
  ports:
  - port: 8080
    targetPort: 8080
  selector:
    app: sandbox-backendapp
```