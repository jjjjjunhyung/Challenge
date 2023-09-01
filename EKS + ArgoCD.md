### 1. ci/cd
- challenge <br>
 Multi region, multi project로 구성되어 있는 eks 서비스들을 수동으로 sync 하기 어려움 <br>
 배포 과정을 일관화된 방법으로 체계적으로 관리하고 자동화할 필요성 <br>
- solution <br>

### 2. Auto Scaling
### 3. Deployment Strategy
- challenge <br>
 Eks rolling update 사용시 안정적이고 서비스 가용성을 유지할 수 있지만 배포시간이 길고 롤백이 어려움 <br>
- options <br>
  - blue/green <br>
  - canary <br>
  - A/B testing <br>
- challenge
