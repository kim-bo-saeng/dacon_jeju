# dacon_jeju
#### 1. 데이콘의 제주신용카드 빅데이터 경진대회에 참여하였습니다.
#### 2. 지속적으로 코드를 업데이트 하고 분석을 진행하겠습니다.
#### score
 - 1차 제출(2020.07.08) : 7.09526 / 189등 => 데이콘에서 제공한 기본베이스라인 코드 실행 / 사용모델 : RandomForestRegressor
 - 2차 제출(2020.07.10) : 7.03975 / 173등 => 데이콘에서 제공한 기본베이스라인 코드에 하이퍼파라미트 튜닝 / 사용모델 : RandomForestRegressor
 - 튜닝한 하이퍼파라미터: max_depth,max_features 조정 , n_estimator는 구글코랩 제공RAM의 한계로인하여 많이 높여서 사용하지 못함
 - 3차 제출(2020.07.13) : 7.03975 / 225등 => 학습데이터에서 종속변수값(예측하려는값) outlier 제거후 모델학습진행
 - 자체예측력은 올랐으나 public예측값의 변화 없음
