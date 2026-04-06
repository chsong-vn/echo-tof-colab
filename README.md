# ECHO-TOF 데이터 분석

원본 EchoMS TOF 질량분석 데이터를 처리하고 분석하는 파이프라인입니다.

## ECHO-TOFMS (분석 워크플로우)

| # | Notebook | 내용 |
|---|----------|------|
| 01 | [Setup / TIC / Baseline](ECHO-TOFMS/01%20Setup%20TIC%20Baseline.ipynb) | 환경설정, mzML 로드, TIC 시각화, SNIP 베이스라인 보정 |
| 02 | [Mass Spectrum](ECHO-TOFMS/02%20Mass%20Spectrum.ipynb) | 특정 시점의 전체 mass spectrum 확인 |
| 03 | [XIC Extraction](ECHO-TOFMS/03%20XIC%20Extraction.ipynb) | 화합물별 XIC 추출, 검출/비검출 비교 |
| 04 | [MS/MS & Fragment](ECHO-TOFMS/04%20MSMS%20Fragment.ipynb) | MS/MS fragmentation, fragment 매칭 |
| 05 | [Fragmentation Prediction](ECHO-TOFMS/05%20Fragmentation%20Prediction.ipynb) | 분자 구조 기반 fragmentation 예측 |
| 06 | [Summation Integration](ECHO-TOFMS/06%20Summation%20Integration.ipynb) | Echo drop별 Summation 적분 |
| 07 | [Parameter Sensitivity](ECHO-TOFMS/07%20Parameter%20Sensitivity.ipynb) | tolerance_ppm, half_window 파라미터 분석 |
| 08 | [Relative Ion Abundance](ECHO-TOFMS/08%20Yield%20Composition.ipynb) | Drop별 조성비 분석 |
| 09 | [m/z Prediction](ECHO-TOFMS/09%20mz%20Prediction.ipynb) | 화학식 → 이론 m/z 계산 |
| 10 | [Formula Identification](ECHO-TOFMS/10%20Formula%20Identification.ipynb) | 미지 피크 → 분자식 역추정 + fragmentation 검증 |
| 11 | [Fragmentation Assignment](ECHO-TOFMS/11%20Fragmentation%20Assignment.ipynb) | MS/MS fragment 자동 할당 |
| 12 | [Reaction Prediction](ECHO-TOFMS/12%20Reaction%20Prediction.ipynb) | 반응 부산물 예측 + 실측 확인 |
| 13 | [Full Pipeline](ECHO-TOFMS/13%20Full%20Pipeline.ipynb) | 반응 스킴 → 자동 분석 → 조성비 |

## Formula Finder (코드 풀이)

`echo_tof/` 패키지의 내부 동작 원리를 단계별로 설명합니다.

| # | Notebook | 내용 |
|---|----------|------|
| 01 | Formula Enumeration | 질량 기반 분자식 열거 알고리즘 |
| 02 | Isotope Calculator | 동위원소 분포 계산 (컨볼루션) |
| 03 | Pattern Matching | 이론 vs 실측 패턴 비교 + 화학 필터링 |
| 04 | Formula Finder Pipeline | 전체 파이프라인 + 4가지 오차 순위 |

## 데이터

- `data/mzml/20260330_TOFMS.mzML` — TOF-MS full scan (495 spectra)
- `data/mzml/20260330_MRMHR_Q1Q3_Final.mzML` — MRM-HR (MS1 + MS/MS)
- `data/Explosives_EchoMS_20260331.xlsx` — 화합물 목록, MRM transitions
