# 비기능 요구사항 (Non-Functional Requirements)

## 성능
- 평균 응답 속도: 200ms 이하
- 동시 사용자: 1,000명 이상 처리 가능

## 보안
- 모든 통신은 HTTPS를 사용
- JWT 기반 인증 및 권한 관리
- 비밀번호는 해싱 저장 (bcrypt 이상)

## 운영
- 로깅/모니터링 표준 수립 (예: OpenTelemetry)
- 장애 발생 시 알림 (Slack, PagerDuty 등)
- 무중단 배포(Blue-Green, Canary)