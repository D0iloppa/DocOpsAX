# 📦 Doc-Normalizer (Doc-Nrm) v1.0.0

📌 비정형 문서(HWP, PDF 등)를 **AI-Ready Canonical JSON 데이터**로 정제하는  
독립 정규화(Normalization) 모듈입니다.

본 모듈은 문서의 **시각적 치장 요소를 제거**하고,  
AI가 즉시 학습·검색·추론에 활용할 수 있는  
**의미 구조 기반 데이터 자산**을 생성합니다.

---

## ✅ 주요 기능

### 1. 멀티 포맷 컬렉터 (Collector)
- 전자결재, 파일 서버, 외부 API로부터 문서 자동 수집
- 지원 포맷: **HWP, HWPX, DOCX, PDF**

### 2. 레이아웃 분석 엔진
- 다단 문서, 중첩 표, 차트 등 복잡한 행정 문서 구조 분석
- 레이아웃을 파괴하지 않고 **의미 단위로 구조 보존**

### 3. 지능형 디노이징 (Denoising)
- 폰트, 색상, 도형, 쪽번호 등  
  AI 학습에 불필요한 **치장 요소 제거·축약**
- 의미 훼손 없는 최소 제거 정책 적용

### 4. Canonical 구조화
- 헤딩 계층(Tree)
- 본문 블록(Block)
- 문서 메타데이터

위 요소를 결합한 **표준 Canonical JSON 출력**

### 5. 근거 좌표 매핑
- 변환된 텍스트가 원본 문서의
  - 페이지 번호
  - 좌표 위치 (x, y)
- 를 유지하여 **근거 추적(Citation) 가능성 확보**

---

## 🧱 구성 요소

| 구성 요소 | 설명 |
|---|---|
| DocCollector.java | 파일 시스템 및 외부 API 연동 문서 수집 모듈 |
| HwpParserEngine.java | HWP / HWPX 바이너리 분석 및 텍스트 추출 |
| LayoutAnalyzer.java | 섹션, 표, 차트 등 레이아웃 구조 판별 |
| NormalizerLinter.java | 정규화 결과물 누락 및 구조 정합성 검사 |
| CoordinateMapper.java | Canonical Block ↔ 원본 좌표 매핑 엔진 |

---

## 🧾 로그 설정 (Log4j2)

본 모듈은 **데이터 리니지(Data Lineage)** 확보를 위해  
모든 변환 과정을 상세히 로깅합니다.

- 기본 정책
  - 정규화 성공 / 실패 여부
  - 변환 소요 시간 기록

- 파일 로깅
  - logs/normalization.log
  - 실패 시 원본 문서의 포맷 특성 함께 아카이빙

---

## 🛠️ 환경 및 스펙

- Language: Java 11  
- Encoding: UTF-8  
- Dependency:
  - MyBatis 3.5.x (메타데이터 저장)
  - Apache POI
  - Hancom GSDK
- Interface: REST API (JSON Response)

---

## 📁 디렉토리 구조 (요약)
```
src/
├── main/
│   ├── java/
│   │   ├── collector/     # 문서 수집 로직
│   │   ├── parser/        # 포맷별(HWP/PDF) 파싱 엔진
│   │   ├── normalizer/    # Canonical JSON 변환 핵심 로직
│   │   └── util/          # OCR 및 이미지 처리 유틸
│   ├── resources/
│   │   ├── rules/         # 디노이징 가이드라인 (YAML/XML)
│   │   └── mapper/        # 변환 이력 관리 SQL
```
---

## 🚀 시작하기

### 1. Git Clone
git clone https://github.com/D0iloppa/Doc-Normalizer.git

### 2. 변환 API 호출 예시
```
POST /api/v1/normalize

Response (Canonical JSON)
{
  "doc_id": "GOV_2026_001",
  "sections": [
    {
      "heading": "2025년도 사업 계획",
      "level": 1,
      "blocks": [
        {
          "type": "paragraph",
          "text": "...",
          "citations": "page 1, [x,y]"
        }
      ]
    }
  ]
}
```
