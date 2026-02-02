# 프루프리딩 보고서

## 문서 정보
- **검토 대상:** `step5_draft_method.md`, `step5_draft_results.md`
- **검토일:** 2025-02-02

---

## 1. Methods 평가 결과

### 1.1 Reproducibility (재현성)

**현재 상태:** 양호

**강점:**
- 소프트웨어 버전 명시 (Python 3.11, pandas, numpy, scipy)
- QC 기준 구체적 (10개 미만 응답, straight-lining)
- 계산 공식 제시 (Ideology, H-H, CR)

**구체적 문제점:**
- 데이터 수집 기간 미기재
- 코드/데이터 공개 URL 미기재
- 랜덤 시드 미기재 (해당 시 필요)

**리뷰어 예상 질문:**
- "데이터는 언제 수집되었는가?"
- "분석 코드를 어디서 확인할 수 있는가?"

**개선 방안:**
- 데이터 수집 기간 추가 (예: "between 2013 and 2017")
- 코드 공개 여부 명시 (예: "Analysis code is available at [URL]")

---

### 1.2 Controls (통제)

**현재 상태:** 양호

**강점:**
- Limitations 섹션에서 온라인 샘플 대표성 한계 인정
- QC 절차로 저품질 응답 제외

**구체적 문제점:**
- 자기선택 편향(self-selection bias) 명시적 언급 부족
- 인구통계적 특성 기술 없음 (성별, 연령 분포 등)

**리뷰어 예상 질문:**
- "참가자의 인구통계적 특성은 어떠한가?"
- "온라인 참가자들이 일반 인구와 어떻게 다를 수 있는가?"

**개선 방안:**
- 인구통계적 기술통계 추가 (Table 또는 텍스트)
- self-selection bias 명시적 언급

---

### 1.3 Sample size/power (샘플/검정력)

**현재 상태:** 양호

**강점:**
- 최소 N=100 기준과 근거 (SE < 0.1) 제시
- 다중 비교 보정 설명 (63 comparisons, |CR| > 3.0)

**구체적 문제점:**
- 사전/사후 검정력 분석 없음
- 효과 크기 해석 기준 미제시

**리뷰어 예상 질문:**
- "이 표본 크기로 어느 정도의 효과 크기를 검출할 수 있는가?"

**개선 방안:**
- 사후 검정력 분석 추가 (선택적)
- 또는 "검정력 분석은 수행하지 않았으나, 대규모 표본으로 인해 작은 효과도 검출 가능" 명시

---

### 1.4 Statistical appropriateness (통계 적절성)

**현재 상태:** 양호

**강점:**
- CR 공식 및 유의성 기준 명확
- 다중 비교 보정 (|CR| > 3.0, p < .003)

**구체적 문제점:**
- 정규성 가정 검토 미언급
- 상관계수의 p값 보고 기준 미명시

**리뷰어 예상 질문:**
- "정규성 가정은 검토했는가?"

**개선 방안:**
- "Given the large sample size, we relied on the central limit theorem for normal approximation" 추가

---

### 1.5 Validation (타당성)

**현재 상태:** 보통

**구체적 문제점:**
- 척도 신뢰도(Cronbach's α) 미보고
- 복합 척도(Ideology, H-H)의 타당성 근거 부족

**리뷰어 예상 질문:**
- "척도의 신뢰도는 어떠한가?"
- "Ideology 계산식의 타당성 근거는?"

**개선 방안:**
- 신뢰도 보고 추가 (또는 기존 문헌 인용)
- 복합 척도 계산식의 출처 인용 (예: Lanning et al., 2022)

---

## 2. Results 평가 결과

### 2.1 문장별 분석

| # | 원문 | Claim Type | Evidence | Risk | 수정 필요 |
|---|------|------------|----------|------|-----------|
| 1 | "Sample sizes varied across scales due to the planned missingness design" | General | Direct | 1 | 없음 |
| 2 | "suggesting a strong positive association that may reflect conceptual overlap" | Correlational | Direct | 3 | 없음 (적절한 hedging) |
| 3 | "indicating that openness is associated with more progressive ideological views" | Correlational | Direct | 2 | 없음 |
| 4 | "These patterns are consistent with theoretical expectations" | General | Indirect | 2 | 없음 |
| 5 | "suggesting lower levels of emotional instability in this sample" | Correlational | Indirect | 5 | 권장 |
| 6 | "indicating more progressive ideological orientation" | Correlational | Direct | 3 | 없음 |
| 7 | "These findings suggest statistically significant regional variation that may be related to cultural, economic, or historical factors" | Correlational | Indirect | 5 | 권장 |

### 2.2 Overclaiming 현황

- **고위험 (Risk ≥ 7):** 0개
- **중위험 (Risk 4-6):** 2개
- **저위험 (Risk 1-3):** 5개

### 2.3 가장 위험한 Overclaim Top 3

#### 1. "suggesting lower levels of emotional instability in this sample"
- **위험도:** 5/10
- **문제점:** "emotional instability"는 Neuroticism의 해석이지만, 자기보고 점수가 실제 정서적 안정성을 직접 반영한다고 단정하기 어려움
- **수정안:** "which corresponds to lower self-reported neuroticism scores"

#### 2. "regional variation that may be related to cultural, economic, or historical factors"
- **위험도:** 5/10
- **문제점:** 문화적/경제적/역사적 요인과의 관계는 추측이며, 데이터로 직접 검증되지 않음
- **수정안:** "regional variation in self-reported personality traits. The sources of this variation remain unclear and could potentially include cultural factors, though alternative explanations such as sampling differences cannot be excluded."

#### 3. "lower scores on the Honesty-Humility composite"
- **위험도:** 3/10
- **문제점:** 경미하지만, H-H가 낮다는 것이 실제로 "덜 정직하다"는 의미로 오해될 수 있음
- **수정안:** "lower scores on the self-reported Honesty-Humility composite scale"

---

## 3. 종합 권고

### Must Fix (반드시 수정)

- [ ] **Results - Florida 문장:** "suggesting lower levels of emotional instability" → "which corresponds to lower neuroticism scores"
- [ ] **Results - 마지막 문단:** 대안 설명을 더 강조하고, 인과적 해석 가능성 명시적 배제

### Should Fix (권장 수정)

- [ ] **Method - Participants:** 데이터 수집 기간 추가
- [ ] **Method - Data Analysis:** 코드 공개 URL 또는 공개 계획 명시
- [ ] **Method - Measures:** 척도 신뢰도 보고 또는 기존 문헌 인용
- [ ] **Results - State-Level:** "self-reported" 명시 추가

### Nice to Have (선택적 개선)

- [ ] **Method - Participants:** 인구통계적 특성 기술통계 추가
- [ ] **Method - Data Analysis:** 정규성 가정 관련 설명 추가
- [ ] **Results - Correlations:** p값 추가 (예: r = .79, p < .001)

---

## 4. 수정 전후 비교

| 위치 | 원문 | 수정안 | 이유 |
|------|------|--------|------|
| Results §3 | "suggesting lower levels of emotional instability in this sample" | "which corresponds to lower self-reported neuroticism scores" | 자기보고 점수 ≠ 실제 정서 상태 |
| Results §3 | "indicating more progressive ideological orientation and lower scores on the Honesty-Humility composite" | "indicating lower scores on the self-reported Ideology (more progressive orientation) and Honesty-Humility composite scales" | self-reported 명시 |
| Results §3 | "regional variation in personality traits that may be related to cultural, economic, or historical factors" | "regional variation in self-reported personality traits that could potentially be related to cultural, economic, or historical factors, although the present data cannot establish such links" | 인과/기전 추론 완화 |
| Method §1 | "We recruited participants through the SAPA..." | "We recruited participants through the SAPA online platform (Condon & Revelle, 2014) between 2013 and 2017." | 수집 기간 추가 |

---

## 5. 종합 평가

### 전반적 품질: **양호 (Good)**

**강점:**
- APA 형식 준수
- 구체적인 통계값 제시
- 다중 비교 보정 설명
- Limitations 섹션 포함
- 대부분 보수적인 표현 사용 ("suggesting", "may", "is associated with")

**개선 필요:**
- 일부 문장에서 self-reported 점수를 실제 특성처럼 기술
- 지역 차이의 원인에 대한 추측이 데이터 범위를 약간 초과
- 척도 신뢰도 미보고

**결론:**
초안의 전반적인 품질은 양호하며, 대부분의 문제점은 경미합니다. 위의 Must Fix 항목 2개와 Should Fix 항목 4개를 반영하면 Nature 수준의 리뷰에도 대응할 수 있는 수준이 될 것입니다.
