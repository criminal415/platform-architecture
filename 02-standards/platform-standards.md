# 플랫폼 표준 (Platform Standards) – Bootstrap 단계

본 문서는 **서비스가 아직 없는 상태**에서 플랫폼 공통으로 적용되는 최소 운영 기준을 정의한다.  
성능/가용성/인증/데이터 기준은 **서비스가 추가될 때 각 서비스 문서에서 정의한다.**

---

## 1) 관측성(Observability)
- **개인정보/비밀정보 금지**: 로그/트레이스에 비밀번호, 토큰, 주민번호 등 PII/시크릿 남기지 않음(마스킹/드롭 필수).
- 로그: 구조화 로그(JSON), 표준 필드 `ts`, `level`, `trace_id`, `span_id`, `user_id?`, `msg` (수집: Grafana, Loki)
- 메트릭: 요청 지연(p50/p95), 에러율, 큐 길이 (Prometheus)
- 트레이싱: 미정
- 대시보드: Grafana
- 알림: 미정

---

## 2) 배포 & 변경관리 (Kubernetes, Jenkins)
- **Infrastructure as Code**: 모든 배포 정의/환경은 Git에 버전 관리
- **Immutable 배포**: 컨테이너 이미지는 불변, 항상 새 버전으로 교체
- 배포 전략: **RollingUpdate (기본)**
- 실패 대응: 배포 실패/헬스체크 악화 시 자동 롤백(runbook 포함)
- DB 마이그레이션 원칙: **expand → migrate → contract** (뒤호환 유지)

---

## 3) 런타임 위생(Hygiene)
- 헬스체크: `livenessProbe`, `readinessProbe` 엔드포인트 필수
- 자원 관리: 컨테이너 `CPU/메모리 requests/limits` 정의
- 설정 관리: 12-Factor 원칙 **최대한 수용**, 미적용은 ADR로 기록

---

## 4) 보안(Security)
- 외부 트래픽: **TLS 1.2+** 암호화 (dev/test: self-signed)
- 내부 통신: **NetworkPolicy**로 서비스 간 접근 제한
- 포트/프로세스 최소화: 불필요한 포트 개방 금지
- 비밀정보: 코드/이미지에 하드코딩 금지 → **Kubernetes Secret** 사용
- 컨테이너: **root 권한 금지** (`runAsNonRoot: true`)
- 이미지: 불필요한 패키지 제거 → 공격 표면 최소화

---

## TODO (서비스 추가 시 정의 예정)
- **인증 & 권한**
- **성능 SLO**
- **데이터 관리**
- **알림 정책**