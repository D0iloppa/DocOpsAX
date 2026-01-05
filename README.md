# 🐋 DocOps AX Platform (v1.0.0)

> **Turning TB-scale Document Corpora into AI-Ready Data Assets**

📌 비정형 문서(HWP, PDF 등)를 정규화·지식화·거버넌스화하여  
AI가 즉시 활용 가능한 **“API 데이터 자산”**으로 만드는 통합 플랫폼

---

## 0. Summary

조직의 AI 전환(AX)은 모델 성능보다 **데이터 준비 상태(AI-Ready)**에서 성패가 갈립니다.  
본 플랫폼은 TB급으로 축적된 레이아웃 중심의 비정형 문서를  **Canonical Data(표준 구조)**로 정제하여,

- 검색 가능
- 근거 추적 가능
- 감사 가능한

**데이터 자산**으로 전환합니다.

---

## 🧱 4대 핵심 모듈 (4-Axis Architecture)

본 플랫폼은 **4개의 독립 모듈**로 구성되며,  
각 모듈은 **단독 제품(Product)** 으로도 동작 가능하도록 설계되었습니다.

| 모듈명 | 핵심 역할 | 독립적 책임 범위 | 제품 가치 |
|---|---|---|---|
| **Doc-Nrm** | 정규화 (Normalization) | 다양한 포맷을 의미 구조 기반 Canonical 데이터로 변환 | 포맷 파편화 해소 · 데이터 정제 |
| **Doc-KB** | 지식화 (Index / KB) | 권한 기반 검색 및 근거 기반 Q&A 제공 | 실무 지식 탐색 · 재사용 |
| **Doc-GV** | 거버넌스 (Governance) | 온프렘 보안 · 전 구간 감사 · 리니지 추적 | 데이터 신뢰성 · 규정 준수 |
| **Doc-Ath** | 작성 체계 (Authoring) | 구조화 작성 UI · 품질 린터(Linter) | 치장 비용 절감 · 품질 상향 |

---

## 📌 AI-Ready 성숙도 모델 (Maturity Levels)

플랫폼 도입을 통해 조직의 문서 자산을 **단계적으로 고도화**합니다.

- **Level 1** — 단순 텍스트 추출  
  *(구조·근거 미비)*

- **Level 2** — 구조 정규화  
  *(섹션·표 보존, 표준 메타데이터 확보)*

- **Level 3** — 지식화  
  *(권한 기반 접근 제어, 근거 포함 Q&A)*

- **Level 4** — 거버넌스  
  *(전 구간 감사 로그, 데이터 리니지 관리)*

- **Level 5** — 작성 체계 전환  
  *(템플릿·린터 기반 자동 생산, 운영 KPI 관리)*

---

## 📁 프로젝트 구조 (Monorepo 기준)

```text
DocOpsAX/ (Root)
├── Doc-Nrm/     # [Module 1] Ingestion & Normalization Engine
├── Doc-KB/      # [Module 2] Knowledge Base & Hybrid Retrieval
├── Doc-GV/      # [Module 3] Security & Governance Layer
├── Doc-Ath/     # [Module 4] Structured Authoring & Rendering
└── README.md    # Integration & Architecture Guide
```

## 🚀 통합 데이터 파이프라인
본 플랫폼의 모든 모듈은 Canonical JSON 표준 규격을 통해 유기적으로 연동됩니다.

1. Ingestion & Normalize
    - Doc-Nrm이 원본 문서의 노이즈를 제거
    - 좌표 기반 의미 구조가 매핑된 Canonical JSON 생성

2. Indexing
    - Doc-KB가 ACL 정보를 포함해 벡터·키워드 색인 수행

3. Retrieval
    - 질문에 대한 답변과 함께 원본 페이지 좌표가 포함된 근거 스니펫 반환

4. Governance
    - 수집 → 변환 → 색인 → 검색 → 반출
    - 전 과정 이력 추적 및 감사 기록

## 📊 품질 · 성능 지표 (KPI)

정규화 품질
- 헤딩 계층 정확도: 98% 이상
- 표 데이터 보존율: 95% 이상

시스템 성능
- p95 응답 시간 250ms 이하

비즈니스 가치
- 보고서 작성 시간 45% 절감
- 자료 검색 시간 60% 단축

🛠️ 환경 및 공통 스펙

| 구분 | 내용 |
|---|---|
| **작성일** | 2026-01-05 |
| **작성자** | 도일 (Doil) |
| **핵심 인터페이스** | Canonical JSON v1.0 |
| **배포 모델** | On-Premise |
