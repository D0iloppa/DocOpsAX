# ✍️ Doc-Authoring (Doc-Ath) v1.0.0

📌 AI 활용을 전제로 한 **구조화 문서 작성 체계**를 제공하는  
Authoring 모듈입니다.

Doc-Ath는 '문서를 잘 꾸미는 행위'가 아닌,  
**AI-Ready 문서를 처음부터 생산**하는 것을 목표로 합니다.

---

## ✅ 주요 기능

### 1. 구조화 작성 UI
- 섹션·블록 기반 문서 작성
- 자유 서식 금지, 의미 구조 강제

### 2. 품질 린터 (Linter)
- 헤딩 누락, 구조 오류 자동 검출
- AI 학습 부적합 패턴 사전 차단

### 3. 템플릿 기반 작성
- 보고서·계획서·업무보고 표준 템플릿 제공
- 조직 단위 템플릿 관리

### 4. Canonical 즉시 생성
- 작성과 동시에 Canonical JSON 생성
- Doc-Nrm 의존 없이 바로 연계 가능

---

## 🧱 구성 요소

| 구성 요소 | 설명 |
|---|---|
| StructuredEditor | 구조화 편집기 |
| TemplateManager | 템플릿 관리 |
| QualityLinter | 품질 규칙 검사 |
| CanonicalEmitter | Canonical JSON 생성 |
| PreviewRenderer | 출력 미리보기 |

---

## 🛠️ 환경 및 스펙

- Frontend: React  
- Backend: Java / Node  
- Output: Canonical JSON v1.0

---

## 🚀 기대 효과
- 문서 생산 시간 단축
- 정규화 비용 최소화
- 조직 전체 문서 품질 상향
