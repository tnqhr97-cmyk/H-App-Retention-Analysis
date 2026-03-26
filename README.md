# H-App-Retention-Analysis
익명 투표 서비스 유저 활성화 및 재출시 전략 분석
> **"초기 유저 80% 이탈 문제를 데이터로 진단하고, 재출시 성공을 위한 3가지 핵심 레버를 도출했습니다."**

## 📌 1. Project Overview
- **배경**: 높은 초기 이탈률로 서비스를 종료했던 소셜 앱의 로그 데이터를 분석
- **목적**: 유저의 잔존 수명(LTV)을 결정짓는 핵심 변수를 발굴하고 재출시 운영 전략 수립
- **나의 역할**: 데이터 전처리 파이프라인(Airflow) 설계 및 XGBoost 기반 수명 예측 모델링

## 🛠️ Tech Stack
- **Languages & Frameworks:** Python
- **Machine Learning:** XGBoost, LightGBM (Feature Importance 분석)
- **Natural Language Processing:** KCBERT (유저 생성 콘텐츠 품질 분류)

## 🔍 2. Core Insights (핵심 발견)
- **[임계 질량]** 특정 커뮤니티(학교) 인원이 **450명**에 도달할 때 유저 활동성이 비약적으로 상승함 (네트워크 효과 입증)
- **[소비 행동]** 결제 여부보다 **'포인트 소비 경험'**이 유저 잔존 수명에 훨씬 강력한 상관관계를 보임
- **[콘텐츠 품질]** KCBERT 모델을 활용해 악성 질문을 걸러내고, 긍정적인 상호작용을 유도하는 운영 로직 제안

## 📂 3. Repository Structure
- `익명 투표 서비스 유저 활성화 및 재출시 전략 분석.pdf`: 상세 분석 보고서
- `/notebooks`: EDA 및 모델링 학습 코드 (Jupyter Notebook)
- `/src`: 데이터 파이프라인 및 전처리 스크립트

## 💻 4. Analysis Process (Code Details)
업로드된 파이썬 스크립트에는 다음과 같은 분석 단계가 포함되어 있습니다.
1. **Data Validation:** `Hackle_Events` 테이블 등 다수 테이블 간 Join을 통한 정합성 검증
2. **Feature Engineering:** 유저별 활동일수(active_days_count), 학교 규모, 포인트 소비 변수 생성
3. **Modeling:** XGBoost 및 LightGBM을 활용한 잔존 수명 예측 및 변수 중요도(SHAP) 산출
4. **Segmentation:** 핵심 지표 기반의 유저 구간 정의 및 구간별 특성 비교 분석
