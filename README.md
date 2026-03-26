# H-App-Retention-Analysis
# 🗳️ 왔노라, 보았노라, 나갔노라: 익명 투표 서비스 재출시 전략 분석

> **"초기 유저 80% 이탈 문제를 데이터로 진단하고, 재출시 성공을 위한 3가지 핵심 레버를 도출했습니다."**

## 📌 Project Overview
- **배경**: 높은 초기 이탈률과 짧은 사용자 수명으로 서비스를 종료했던 소셜 앱의 데이터 복기를 통한 문제 정의
- **목적**: 유저 잔존 수명(active_days_count)에 영향을 미치는 핵심 동인 발굴 및 재출시 운영 전략 수립
- **나의 역할**: 데이터 정합성 검토 및 분석 마스터 테이블 구축, LightGBM 기반 수명 예측 모델링 수행

## 🛠️ Tech Stack
- **Languages:** Python (Google Colab)
- **Libraries:** Pandas, NumPy, XGBoost, LightGBM
- **Natural Language Processing:** KCBERT (질문 콘텐츠 품질 관리 프레임워크 제안)
- **Data Engineering:** SQL (MySQL), Data Cleaning (Hackle_Events 배제 및 데이터 정제)

## 📄 자료 바로가기
- 🎤 [**핵심 요약 발표자료 (PDF)**](./익명%20투표%20서비스%20유저%20활성화%20및%20재출시%20전략%20발표자료.pdf)
- 📝 [**상세 분석 보고서 (PDF)**](./익명%20투표%20서비스%20유저%20활성화%20및%20재출시%20전략%20분석.pdf)
- 💻 [**분석 소스 코드 (Notebook)**](./H_App_Analysis.ipynb.ipynb)

## 💡 Key Insights
1. **데이터 정합성 중심 분석**: 신뢰도가 낮은 `Hackle_Events` 데이터를 배제하고, 실제 유저 행동을 대변할 수 있는 정제된 마스터 테이블을 구축하여 분석의 객관성 확보.
2. **투표 상호작용의 영향**: 단순히 질문을 생성하는 것보다 유저 간 **'투표 상호작용'**이 형성될 때 잔존 수명이 유의미하게 증가함을 입증.
3. **임계 수준(Critical Mass)**: 학교/그룹 규모가 **임계 수준(450명)**에 도달할 때 네트워크 효과로 인해 유저 활동 지표가 비약적으로 상승함을 발견.
4. **소비 경험의 중요성**: 포인트 획득보다 아이템 구매나 질문 열람 등 **'포인트 소비'** 경험이 유저 정착 성공을 결정짓는 핵심 변수임을 도출.

## 💻 Analysis Details
- **Data QA & Cleaning:** `Hackle_Events` 테이블의 결측치 및 중복 이슈를 파악하여 분석 제외 결정 후 데이터 정합성 확보
- **Feature Engineering:** 유저별 활동일수, 상호작용 비율(giver_ratio), 학교 유저 수 등 핵심 변수 생성
- **Modeling:** XGBoost 모델을 통해 정착 성공(23일+)과 실패 집단 간의 특성 차이를 데이터로 증명
