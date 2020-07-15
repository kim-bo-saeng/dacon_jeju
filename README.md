# dacon_jeju
#### 1. 데이콘의 제주신용카드 빅데이터 경진대회에 참여하였습니다.
#### 2. 지속적으로 코드를 업데이트 하고 분석을 진행하겠습니다.
#### score
 - 1차 제출(2020.07.08) : 7.09526 / 189등 => 데이콘에서 제공한 기본베이스라인 코드 실행 / 사용모델 : RandomForestRegressor
 - 2차 제출(2020.07.10) : 7.03975 / 173등 => 데이콘에서 제공한 기본베이스라인 코드에 하이퍼파라미트 튜닝 / 사용모델 : RandomForestRegressor
 - 튜닝한 하이퍼파라미터: max_depth,max_features 조정 , n_estimator는 구글코랩 제공RAM의 한계로인하여 많이 높여서 사용하지 못함
 - 3차 제출(2020.07.13) : 7.03975 / 225등 => 학습데이터에서 종속변수값(예측하려는값) outlier 제거후 모델학습진행
 - 자체예측력은 올랐으나 public예측값의 변화 없음
 - 4차 제출(2020.07.14) : 6.98248 / 242등 => 새로운 피쳐 생성후 model학습 진행, 등수는 의미 없으며 모델성능이 조금 향상됨
 - 새로 생성한 피쳐는 카드사용지역과 거주지역이 같은지 다른지에 따라 생활권 비생활권의 피쳐를 생성하여 학습진행
 - 5차 제출(2020.07.14) : 8.2871435947 / 303등 : 통계청의 소비자동향지수데이터를 이용하여 새로운 피쳐를 생성하였으나 규칙상 2020년3월까지
 - 데이터만 사용이 가능하여 정작 예측을 해야될 2020년4월/7월에 필요한 2020년4,5,6월 동향지수 데이터를 사용하지 못함 그래서 2020년3월까지의
 - 데이터를 이용하여 2020년4월/7월의 소비자동향지수를 예측하여 예측한 동향지수를 가지고 학습을 진행하였으나 모델의 성능은 더안좋아짐
 - 아마도 다중공선성의 문제가 발생하였을것으로 예상됨 => 추후 이것은 다른방법으로 이용해볼것을 고민해야될듯함
 - 6차 제출(2020.07.15) : 7.659012519 / 308등 => 결제고객수와 결제건수의 차이를 이용하여 새로운 피쳐를 생성함
 - 새로 생성된 피쳐의 내용은 결제고객수가 더 많으면 "결제취소있음" 결제건수가 더많으면 "여러번결제" 같으면 "일반결제" 라는 내용을
 - 넣어 업종별로 고객들이 취소가 많은지 단골이 많은지 등을 구분하여 학습시켰으나 효과는 없었음
