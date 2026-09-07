### 안녕하세요, 데이터 분석/ML을 공부하고 있는 박찬종입니다.

1~2년 전 수업·팀 과제로 진행했던 분석들을 **지금의 기준으로 다시 검증하고 재구축**하는 작업을 하고 있습니다.
결과 수치보다 **그 수치를 믿을 수 있는지 확인하는 과정**을 남기려고 합니다.

#### 📊 [python-data-portfolio](https://github.com/jongchacha16-jpg/python-data-portfolio)

재검증 과정에서 실제로 뒤집힌 결론들입니다.

- **"정확도 95%"가 뇌졸중 환자를 한 명도 찾지 못하는 모델의 수치**였음을 확인
  → 지표를 PR-AUC로 전환하고, 리샘플링은 훈련 fold 내부에서만 적용해 재측정
- **리키지라고 알고 있던 변수가 실제로는 중복 변수**였음을 통화별 환산비로 규명
  → 문서의 설명과 코드가 하는 일이 달랐던 사례
- **결측 삭제가 뇌졸중 사례의 27.7%를 선별적으로 제거**하고 있었음을 카이제곱 검정으로 확인
- 특성 중요도가 전부 0인데 **R²=1.0으로 기록된 랜덤포레스트 결과를 무효로 판정**

재구축 노트북은 생성 스크립트 + `nbconvert --execute`로 만들어,
"실행되지 않는데 출력만 있는 셀"이 생길 수 없게 했습니다.

#### 📱 Flutter / Dart

- [flutter_workout](https://github.com/jongchacha16-jpg/flutter_workout) — 운동 기록 앱.
  `go_router` 중첩 라우팅, `shared_preferences` 영속성, `FutureBuilder` 컴포넌트화
- [flutter-todo-app](https://github.com/jongchacha16-jpg/flutter-todo-app) — 할 일 관리 앱.
  Hive 영속성, 계층 분리 구조, 키워드 기반 카테고리 자동 분류
- [flutter_application_1](https://github.com/jongchacha16-jpg/flutter_application_1) — Dart 문법·비동기 첫 학습 기록

#### 🛠 Skills

**분석·모델링** Python · pandas · numpy · scikit-learn · XGBoost · imbalanced-learn · statsmodels
**시각화** matplotlib · seaborn
**앱 개발** Flutter · Dart
**학습 중** MongoDB · Elasticsearch
