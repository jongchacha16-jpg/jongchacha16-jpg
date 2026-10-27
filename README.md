### 안녕하세요, 데이터 분석/ML을 공부하고 있는 박찬종입니다.

1~3년 전 수업·팀 과제로 진행했던 분석들을 **지금의 기준으로 다시 검증하고 재구축**하는 작업을 하고 있습니다.
결과 수치보다 **그 수치를 믿을 수 있는지 확인하는 과정**을 남기려고 합니다.

최근에는 그 기준을 과거 작업뿐 아니라 **지금 하는 작업에도 적용**하는 쪽으로 넓히고 있습니다 —
분석을 서비스로 만들어보고, 개선과 잡음을 구분하는 실험 설계를 먼저 세우는 식으로요.

## 프로젝트

| # | 프로젝트 | 한 줄 요약 | 핵심 스택 | 상세 |
|---|---|---|---|---|
| 1 | [**표정 분류 CNN → 이모지 매칭** ↗](https://github.com/jongchacha16-jpg/python-data-portfolio/tree/master/%EC%9D%B8%EA%B3%B5%EC%A7%80%EB%8A%A5%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8) | 3년 묵은 미완성 과제를 버그 수정·재학습으로 완성, 제로샷 LLM과 성능 비교까지 | TensorFlow/Keras | [노션 ↗](https://topaz-soarer-390.notion.site/3cc28debe9df80848e44ff9232978b7c) |
| 2 | [**Photo2Emoji 서비스** ↗](https://github.com/jongchacha16-jpg/python-data-portfolio/tree/master/photo2emoji-service) | 위 파이프라인을 `POST /predict` API로 제품화 (pytest 10개·Docker 검증) | FastAPI, Docker | [노션 ↗](https://topaz-soarer-390.notion.site/3ff28debe9df8032a368e18059c584cd) |
| 3 | [**분산 DB 회의실 예약** ↗](https://github.com/jongchacha16-jpg/python-data-portfolio/tree/master/%EB%B6%84%EC%82%B0%EC%B2%98%EB%A6%AC%EC%8B%9C%EC%8A%A4%ED%85%9C_%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8) | MongoDB Replica Set failover 실측 + 보안 감사 2회 | MongoDB, Docker | [노션 ↗](https://topaz-soarer-390.notion.site/3ff28debe9df80f2ac09e4bdb2e648a3) |
| 4 | [**와인 품질 회귀분석** ↗](https://github.com/jongchacha16-jpg/python-data-portfolio/tree/master/%ED%9A%8C%EA%B7%80%EB%B6%84%EC%84%9D_%EC%A1%B0%EB%B3%84%EA%B3%BC%EC%A0%9C) | 두 개 트랙 재검증 — 주장·절차 13건 중 12건 정정 | statsmodels | [노션 ↗](https://topaz-soarer-390.notion.site/3cc28debe9df80e5bf7ecbf4ea0437d0) |
| 5 | [**뇌졸중 발병 예측** ↗](https://github.com/jongchacha16-jpg/python-data-portfolio/tree/master/%EB%8D%B0%EC%82%AC%ED%94%84_%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8) | "정확도 95%의 함정"을 불균형 관점으로 재구축 | scikit-learn | [노션 ↗](https://topaz-soarer-390.notion.site/65628debe9df830eb87381195d7f537e) |
| 6 | [**데이터 직무 연봉 예측** ↗](https://github.com/jongchacha16-jpg/python-data-portfolio/tree/master/MachineLearning_Data_Related_Job_Salary) | 리키지로 알던 변수의 정체를 코드로 규명 | scikit-learn | [노션 ↗](https://topaz-soarer-390.notion.site/85628debe9df82fd959c81bacdb35ed1) |
| 7 | [**항공사 승객 만족도 예측** ↗](https://github.com/jongchacha16-jpg/airline-satisfaction-prediction) | 0.0013 개선을 잡음과 구분하는 실험 프로토콜 설계 (Kaggle) | LightGBM, Optuna | [노션 ↗](https://topaz-soarer-390.notion.site/40028debe9df8046a90bda5ccb613a72) |
| 8 | [**Flutter 앱 개발** ↗](https://github.com/jongchacha16-jpg/flutter_workout) | 학습 3단계 — 라우팅·영속성·비동기를 갖춘 [운동 기록 앱 ↗](https://github.com/jongchacha16-jpg/flutter_workout)과 Hive·계층 분리 구조의 [할 일 앱 ↗](https://github.com/jongchacha16-jpg/flutter-todo-app) (저장소 3개) | Flutter, Dart | [노션 ↗](https://topaz-soarer-390.notion.site/3cc28debe9df80d4a98be754d2cf1098) |

> 1~6번은 [python-data-portfolio](https://github.com/jongchacha16-jpg/python-data-portfolio) 안의 폴더이고, 7·8번은 별도 저장소입니다.
> **처음 보신다면 1·7·3번**을 권합니다.

---

#### 📊 [python-data-portfolio](https://github.com/jongchacha16-jpg/python-data-portfolio) — 재검증 기록

재검증 과정에서 실제로 뒤집힌 결론들입니다.

- **"정확도 95%"가 뇌졸중 환자를 한 명도 찾지 못하는 모델의 수치**였음을 확인
  → 지표를 PR-AUC로 전환하고, 리샘플링은 훈련 fold 내부에서만 적용해 재측정
- **리키지라고 알고 있던 변수가 실제로는 중복 변수**였음을 통화별 환산비로 규명
  → 문서의 설명과 코드가 하는 일이 달랐던 사례
- **결측 삭제가 뇌졸중 사례의 27.7%를 선별적으로 제거**하고 있었음을 카이제곱 검정으로 확인
- 특성 중요도가 전부 0인데 **R²=1.0으로 기록된 랜덤포레스트 결과를 무효로 판정**
  → 원인은 `quality`(정답)가 특성 행렬에 그대로 들어간 타깃 누수였습니다
- **학습 데이터의 20%가 조용히 버려지고 있던 CNN 버그**를 찾아 재학습
  → 같은 전체 테스트셋 기준 0.5720 → **0.5954 (+4.1%)**, 3년 만에 혼동행렬로 클래스별 성능 확인
- **자랑하던 RandomForest R² 0.712가 업샘플링을 분할 전에 수행한 누수**였음을 확인
  → 순서만 바로잡으니 **0.548**. 테스트의 59.6%가 훈련에 쌍둥이를 갖고 있었습니다

재구축 노트북은 생성 스크립트 + `nbconvert --execute`로 만들어,
"실행되지 않는데 출력만 있는 셀"이 생길 수 없게 했습니다.
원본 노트북은 수정하지 않고 보존해 **before / after를 비교**할 수 있게 했습니다.

#### 🚀 분석을 서비스와 인프라로

- **Photo2Emoji API** — 노트북에서만 돌던 사진 → 감정 → 이모지 파이프라인을 FastAPI로 제품화.
  `POST /predict`, 웹 데모, **pytest 10개**, venv·Docker 양쪽에서 실측 응답 확인
  *(모델 정확도 자체는 테스트로 단정하지 않았습니다 — 0.5954인 모델에 그런 테스트를 걸면 손댈 때마다 깨집니다)*
- **분산 DB 회의실 예약 시스템** — MongoDB Replica Set 위의 Flask 앱.
  Docker 3노드로 **failover 약 10초 실측**, 보안 감사를 **두 번** 돌려 1차 5건 + 2차 13건 발견
  *(2차의 '높음' 3건만 패치했고 **남은 10건은 미조치임을 문서에 명시**했습니다)*

#### 🔬 [airline-satisfaction-prediction](https://github.com/jongchacha16-jpg/airline-satisfaction-prediction) — 실험 설계

Kaggle Playground S6E10. 목표 개선폭이 0.0013인데 **Fold 간 표준편차가 0.00058**이었습니다.
잡음과 목표의 자릿수가 같아서, 어려운 쪽은 모델링이 아니라
**"지금 올라간 0.0005가 진짜인가"를 판정하는 일**이었습니다.
단계별 개선폭 0.0005는 잡음과 거의 1:1입니다.

- 성능을 재기 전에 채택 기준부터 고정 — *"Pooled OOF 개선 + 5개 Fold 중 4개 이상 개선"*
- 설계한 피처 **4개 중 3개를 기각**. EDA에서 현상이 보여도, 트리가 이미 자력으로 잡고 있으면 기여하지 않습니다
- 대조군에도 실험군과 **같은 다중 시드 처리**를 적용 (안 했다면 이득이 17% 부풀려졌을 값)
- 앙상블 다양성은 Pearson이 아니라 **Spearman**으로 판정 (ROC-AUC는 순위만 사용하므로)

OOF AUC 0.95866 → **0.95994**. 목표 0.9600에는 0.00006 미달했고, 그 사유도 함께 적었습니다.

#### 📱 Flutter / Dart

- [flutter_application_1](https://github.com/jongchacha16-jpg/flutter_application_1) — Dart 문법·비동기 첫 학습 기록
- [flutter_workout](https://github.com/jongchacha16-jpg/flutter_workout) — 운동 기록 앱.
  `go_router` 중첩 라우팅, `shared_preferences` 영속성, `FutureBuilder` 컴포넌트화
- [flutter-todo-app](https://github.com/jongchacha16-jpg/flutter-todo-app) — 할 일 관리 앱.
  Hive 영속성, 계층 분리 구조, 키워드 기반 카테고리 자동 분류

#### 🛠 Skills

**분석·모델링** Python · pandas · numpy · scikit-learn · statsmodels · imbalanced-learn
**GBDT·튜닝** LightGBM · XGBoost · CatBoost · Optuna · 스태킹
**딥러닝** TensorFlow / Keras · PyTorch
**서빙·배포** FastAPI · Docker · pytest
**데이터베이스** MongoDB (Replica Set · GridFS) · Elasticsearch
**시각화** matplotlib · seaborn
**앱 개발** Flutter · Dart

#### 🎯 지금 채우고 있는 것

포트폴리오를 채용 관점에서 스스로 점검해 갭을 정리해 두었고, 순서대로 메우는 중입니다.

- ✅ **서빙·배포 경험** — Photo2Emoji API로 해소
- ✅ **테스트 문화** — pytest 스위트 도입
- ⬜ **SQL 기반 분석 프로젝트** — 아직 없습니다. MongoDB가 유일한 DB 경험입니다
- ⬜ **데이터 수집 경험** — 데이터가 전부 공개 데이터셋(Kaggle/UCI/COCO)입니다
- ⬜ **CI** — GitHub Actions로 pytest 자동화
