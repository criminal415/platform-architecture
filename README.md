# Platform Architecture Repository

이 저장소는 플랫폼 및 하위 서비스들의 **아키텍처, 설계 문서, 의사결정 기록(ADR)** 을 관리합니다.  
모든 변경사항은 Git commit 히스토리와 함께 추적됩니다.

## 디렉토리 구조
- **01-guides/**: 작성 규칙 및 문서 스타일 가이드
- **02-standards/**: 공통 표준 (보안, 네이밍, 관측성 등)
- **03-adr/**: 플랫폼 전역 Architecture Decision Records
- **04-architecture/**: 플랫폼 전체 아키텍처 (C4 모델 기반)
- **10-domains/**: 도메인(BC, Bounded Context) 단위 설계
- **20-services/**: 개별 서비스(마이크로서비스, 앱) 단위 설계
- **90-decisions-log.md**: 주요 결정의 타임라인 요약

## 작성 원칙
1. 모든 주요 결정은 ADR로 남긴다.
2. 문서 수정 시 의미 있는 commit 메시지를 남긴다.
3. 다이어그램은 가능한 한 **텍스트 기반(Mermaid)** 으로 작성한다.