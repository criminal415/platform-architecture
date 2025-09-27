# 문서 작성 & 커밋 메시지 규칙

## 1. 문서 작성 규칙

### 공통 원칙
- 모든 문서는 **Markdown(.md)** 으로 작성한다.  
- 다이어그램은 **텍스트 기반(Mermaid 권장)** 으로 작성한다.  
- 파일명은 **영문 소문자 + 하이픈(-)** 을 사용한다.  

---

## 2. 커밋 메시지 규칙

### 기본 형식
- **type**: 변경의 성격 (필수)  
- **scope**: 변경 범위 (선택, 괄호 생략 가능)  
- **subject**: 짧은 설명

---

### Type 종류

| Type        | 설명 |
|-------------|------|
| **docs:**   | 문서 작성/수정 (요구사항, 설계, 표준, README, 오타/링크 수정 포함) |
| **adr:**    | Architecture Decision Record 추가/수정 |
| **diagram:**| 다이어그램 추가/수정 (Mermaid) |
| **refactor:**| 문서/폴더 구조 변경 (파일 이동, 이름 변경 – 의미 변화 없음) |
| **style:**  | 문서 포맷팅, 마크다운 스타일 변경 (내용 변화 없음) |
| **chore:**  | 기타 유지보수 (.gitignore, 툴링 설정 등) |

---

### Subject 작성 원칙
- 설명은 한국어 **평서문**으로 작성한다. (예: “추가”, “수정”, “삭제”)
- 문장은 간결하게 (50자 이내)  
- 끝에 마침표(`.`) 붙이지 않음
- 한 줄 커밋 메시지를 기본으로, 필요하면 Body와 Footer를 추가한다.  
 
---

### Scope 작성 가이드
- 플랫폼 전역: `platform`  
- 문서/다이어그램: `docs`, `diagram`  
- (서비스/도메인 스코프는 **추후 서비스 레포에서 사용**)  

---

**예시:**
- docs(platform): 비기능 요구사항 초안 작성
- adr(platform): 0003 Jenkins CI/CD 도입 결정
- diagram(platform): C4 L2 컨테이너 다이어그램 추가
- refactor(platform): 문서 디렉토리 구조 변경
- style: 마크다운 헤딩 레벨 통일
- chore: .gitignore에 drawio 백업 파일 추가

```
adr(auth-service): 0003 session strategy decision
    - Context: 세션 만료 정책 논의  
    - Decision: JWT Refresh Token 채택  
    - Consequences: Redis 기반 세션 관리 불필요
```
