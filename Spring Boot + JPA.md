### 1. Soft Delete
- challenge <br>
 로깅 및 디버깅을 위해 특정 테이블에서의 soft delete 기능 필요 <br>
 특정 칼럼의 값과 관련하여 삭제되지 않은 entity들의 uniqueness는 보장되어야 하되, 삭제된 entity들의 duplicate은 허용되어야 하는 상황 <br>
 Mysql은 Postgre SQL과 다르게 partial index를 지원하지 않음 <br>
- solution <br>
 기존에 존재하던 name 칼럼과 notArchived(1 or null) 칼럼을 새롭게 추가하여 unique constraint 설정

### 2. Entity race condition
- challenge <br>
- solution <br>
 ##### JPA의 @Version 데코레이터(Long, Integer, Short, Timestamp)를 사용하여 Optimistic Lock 방식으로 엔티티의 버전을 관리
  - Default: None
  - LockMode.OPTIMISTIC
  - LockMode.OPTIMISTIC_FORCE_INCREMENT
  - Pessimistic Lock 방식 (DB Lock + Query)
    - LockModeType.PESSIMISTIC_READ
    - LockModeType.PESSIMISTIC_WRITE
    - LockModeType.PESSIMISTIC_FORCE_INCREMENT
 ##### TransactionSynchronizationManager, TransactionSynchronization을 사용하여 afterCommit 함수 override

### 3. JVM GC
- challenge <br>
 JVM을 사용하는 프로젝트의 별도 설정을 해주지 않으면 사용하는 컴퓨팅 자원의 사이즈에 따라 GC 알고리즘이 채택 <br>
 Production 환경에서 관리자가 의도치 않게 어플리케이션이 원시적인 GC 알고리즘을 사용할 수 있음
- solution <br>
  ##### G1 GC
  - 하드웨어가 발전함에 따라 큰 메모리(RAM) 공간을 가지고 있는 멀티 프로세서 시스템에서 빠른 처리 속도를 지원한다. <br>
  - 최소 2 cpu 및 4GB memory 인 환경에서 권장되며 Java 9+부터는 default GC로 채택 <br>
  ###### Serial GC
  - 가장 간단한 GC 구현체이며 싱글 스레드로 동작
  ###### Parallel GC / CMS GC
  - 다수의 스레드를 사용하며, GC 동작 시 최소한의 pause 타임을 가지도록 설계
  ###### Z GC
  -  Java11부터 실험적으로 소개된 확장성 있고 짧은 지연 시간을 갖는 GC

### 4. JPA N+1
- challenge <br>
- solution <br>

### 5. JPA Cache
- challenge <br>
- solution <br>
