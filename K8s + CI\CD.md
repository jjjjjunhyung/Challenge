### 1. ci/cd
- challenge <br>
 Multi region, multi project로 구성되어 있는 eks 서비스들을 수동으로 sync 하기 어려움 <br>
 배포 과정을 일관화된 방법으로 체계적으로 관리하고 자동화할 필요성 <br>
- solution <br>
 CircleCi를 통한 애플리케이션 빌드 후 ArgoCD를 통한 K8s 배포
- pros and cons <br>

### 2. Auto Scaling
- challenge <br>
 서비스 부하가 불규칙한 상황에서 고정된 개수의 instance를 운영하는 것은 비효율적인 상황 <br>
 부하가 집중되는 상황에서는 인스턴스 개수를 늘리고, 그 외의 상황에서는 최소화하는 방식으로 유연하게 운영할 필요성 <br>
- solution <br>

### 3. Deployment Strategy
- challenge <br>
 Eks rolling update 사용시 안정적이고 높은 서비스 가용성을 유지할 수 있지만 배포시간이 길고 롤백이 어려움 <br>
- options <br>
  - blue/green <br>
  - canary <br>
  - A/B testing <br>
