# Container
**컨테이너**란 이미지를 담는 그릇이다. 
이미지 레이어 위에 컨테이너 레이어를 올려놓은 개념이다. 
> **컨테이너 레이어**  
> 이미지 레이어를 실제 사용하기 위한 Readable/Writable 기능을 수행하는 레이어

## Container Runtime
- Image를 Image Registry로 부터 가져와서 Run을 수행한다. Image를 빌드 및 생성 후 Image Registry로 Push 한다.
- Image를 활용하여 Container를 실행 및 관리한다.

**Dockerfile**
``` cmd
FROM	quay.io/webhippie/java:11
RUN chmod 777 /var/log/
WORKDIR	/app
EXPOSE	8080
ADD	./target/sandbox-backendapp-0.0.1-SNAPSHOT.jar /app/sandbox-backendapp-0.0.1-SNAPSHOT.jar
ENTRYPOINT	["java","-jar","/app/sandbox-backendapp-0.0.1-SNAPSHOT.jar"]
```
![캡처](/images/structure-of-container.png)

> **Container Runtime의 비교  (Docker vs CRIO)**
> - Docker는 무겁고 CRIO는 가볍다.  
> - 하나의 Worker Node에서 Docker Engine이 죽으면 모든 Container가 서비스 중단된다. 하지만 CRIO의 경우는 서비스와 독립적이므로 서비스가 유지된다.  
> - Kubernetes 2.0 부터는 Container Runtime으로 Docker를 지원하지 않는다.

