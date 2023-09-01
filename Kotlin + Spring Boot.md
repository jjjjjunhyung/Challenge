### 1. Soft Delete
- challenge <br>
 로깅 및 디버깅을 위해 특정 테이블에서의 soft delete 기능 필요 <br>
 삭제되지 않은 entity들의 unique는 보장되어야 하되, 삭제된 entity들의 duplicate은 허용되어야 하는 상황 <br>
 Mysql은 Postgre SQL과 다르게 partial index를 지원하지 않음 <br>
- solution <br>
### 2. Entity race condition
### 3. JPA N+1
