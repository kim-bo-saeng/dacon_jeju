# dacon_jeju
#### 1. 데이콘의 제주신용카드 빅데이터 경진대회에 참여하였습니다.
#### 2. 지속적으로 코드를 업데이트 하고 분석을 진행하겠습니다.
### 3. 최종 스코어 1.74896 / 2위(최우수상)
#### score
 - 1차 제출(2020.07.08) : 7.09526 / 189등 => 데이콘에서 제공한 기본베이스라인 코드 실행 / 사용모델 : RandomForestRegressor
 - 2차 제출(2020.07.10) : 7.03975 / 173등 => 데이콘에서 제공한 기본베이스라인 코드에 하이퍼파라미트 튜닝 / 사용모델 : RandomForestRegressor
 튜닝한 하이퍼파라미터: max_depth,max_features 조정 , n_estimator는 구글코랩 제공RAM의 한계로인하여 많이 높여서 사용하지 못함
 - 3차 제출(2020.07.13) : 7.03975 / 225등 => 학습데이터에서 종속변수값(예측하려는값) outlier 제거후 모델학습진행
 자체예측력은 올랐으나 public예측값의 변화 없음
 - 4차 제출(2020.07.14) : 6.98248 / 242등 => 새로운 피쳐 생성후 model학습 진행, 등수는 의미 없으며 모델성능이 조금 향상됨
 새로 생성한 피쳐는 카드사용지역과 거주지역이 같은지 다른지에 따라 생활권 비생활권의 피쳐를 생성하여 학습진행
 - 5차 제출(2020.07.14) : 8.2871435947 / 303등 : 통계청의 소비자동향지수데이터를 이용하여 새로운 피쳐를 생성하였으나 규칙상 2020년3월까지
 데이터만 사용이 가능하여 정작 예측을 해야될 2020년4월/7월에 필요한 2020년4,5,6월 동향지수 데이터를 사용하지 못함 그래서 2020년3월까지의
 데이터를 이용하여 2020년4월/7월의 소비자동향지수를 예측하여 예측한 동향지수를 가지고 학습을 진행하였으나 모델의 성능은 더안좋아짐
 아마도 다중공선성의 문제가 발생하였을것으로 예상됨 => 추후 이것은 다른방법으로 이용해볼것을 고민해야될듯함
 - 6차 제출(2020.07.15) : 7.659012519 / 308등 => 결제고객수와 결제건수의 차이를 이용하여 새로운 피쳐를 생성함
 새로 생성된 피쳐의 내용은 결제고객수가 더 많으면 "결제취소있음" 결제건수가 더많으면 "여러번결제" 같으면 "일반결제" 라는 내용을
 넣어 업종별로 고객들이 취소가 많은지 단골이 많은지 등을 구분하여 학습시켰으나 효과는 없었음
 - 7차 제출(2020.07.16) : 7.291081002 / 323등 => 4월,7월의 결제고객수와 결제건수를 각각 예측한뒤 학습데이터에 넣어서 예측을 진행
 가장 결과가 좋았던 기본베이스라인 코드에서 생활권/비생활권 피쳐만 추가하여 학습했던 코드보다 여전히 성능이 향상되지 못함
 - 8차 제출(2020.07.17) : 5.5699394201 / 172등 => 2020년4월 데이터를 예측함에 있어서 주어진 데이터는 2019년1월부터 2020년3월데이터인데
 모든데이터를 사용하지 않고 2019년 2월/3월/4월 , 2020년 2월/3월 데이터만을 모델에 학습하여 2020년4월을 예측하였더니 점수가 크게 향상되었다
 2020년 2월/3월이 코로나의 영향을 많이 받은 시기이고 4월도 마찬가지라 모든 데이터를 사용하는것보다 코로나의 영향을 어떻게 모델이 잘 알수있게
 학습될지를 생각한 결과 필요없는 피쳐들 즉, 오히려 오해를 불러일으킬수 있는 피쳐들을 제거하니 점수가 향상되었음
 - 12차 제출(2020.07.24) : 2.6587105699 / 166등 => 모델 학습에 사용된 피쳐(연/월 데이터 2019.02/03/04 ~ 2020.02.03 + 카드사용지역 + 업종 + 사용자거주지역 + 
 연령 + 생애주기 + 생활권) // 기본 전체 데이터에서 연/월 데이터를 필요한것만 추리고 성별 데이터는 뺐음 또한 이번대회의 데이터는 모두 범주형 데이터로써 예측을 진행하기전 
 예측 탬플릿을 생성하여 카테고리 데이터의 모든 조합을 예측하여 진행이 되는데 학습시키려는 데이터 자체가 모든 범주형 데이터의 조합의 AMT(타겟값)값이 있지 않으므로
 먼저 주어진 데이터에서 모든 조합의 경우를 만들고 빈값은 1로 채워 모델 학습을 진행하였다 그리하여 그 전보다 점수가 2.6XX대로 향상되었다
 - 13차 제출(2020.07.24) : 1.9489019929 / 146등 : 빈값을 0으로 채우고 모델 학습을 진행하였더니 1로 채웠을때보다 점수가 향상되었음 빈값은 0으로 채우는것이 나음
 - 14차 제출(2020.07.24) : 1.5113220604 / 1등(현시점): 13차 제출과 모든것이 동일한 상태에서 RandomForestRegressor모델에서 ExtraTreesRegressor모델로 변경하였더니 점수가 향상됨
 - 15차 제출(2020.07.25) : 1.5775297675 / 136등 : 14차 제출과 동일한 상태에서 뺐던 성별 컬럼을 넣어보고 진행 // 점수는 떨어졌으며 모든 피쳐를 다 사용하는것이 오히려 점수가 안나온다는걸 알게됨
 - 16차 제출(2020.07.25) : 1.5379111233 / 4등 : 14차 이후 부터는 기본적으로 ExtraTreesRegressor모델을 사용하고 사용 피쳐중 연/월 데이터는 2019.02/03/04 ~ 2020.02.03 을 사용하며
 나머지 CARD_SIDO_NM, STD_CLSS_NM, HOM_SIDO_NM 피쳐는 고정으로 사용하고 CARD_CCG_NM, HOM_CCG_NM, CSTMR_CNT, CNT 피쳐은 고정으로 제거한뒤 남은 성별/생애주기/연령 의 피쳐는 빼고넣고 하는 조합을 통해 모델을 향상 시키는 중이며 16차 제출결과는 성별/생애주기/연령을 모두 제거하고 제출한 결과이다
 - 17차 제출(2020.07.25) : 1.4770044178	/ 1등 : 성별 + 생애주기를 사용하여 제출한 결과 이다
 - 4월 데이터 예측은 끝나고 마지막으로 7월 데이터예측을 통해 최종 점수를 평가한다 7월 데이터 예측을 위해 모델은 ExtraTreesRegressor를 사용하며 년/월 데이터는
 EDA를 해본 결과 2019년 1/2/3/4/7월 + 2020년 1/2/3/4월 을 사용하는것이 가장 좋은것으로 판단되며 사용되는 피쳐는 현재 여러경우의 수를 따져가며 그래프를 그려보며 판단중
- 크로스벨리데이션을 통해 최종적으로 사용될 피쳐는 CARD_SIDO_NM, STD_CLSS_NM,HOM_SIDO_NM,AGE,SEX_CTGO_CD,FLC,year,month,MY_HOME 이며 년/월 데이터는 2019년 1월/2월/3월/4월/7월 + 2020년 1월/2월/3월/4월만을 사용하여 모델 학습을 진행하기로하였음 최종예측 파일 제출하였으며 8/10 최종 스코어와 등수가 공개되면 마지막 업로드 예정
- 2020년 7월 예측 결과(최종스코어) : 1.74896 / 2위(최우수상) -> 2019년1/2/3/4/7월 + 2020년1/2/3/4월 데이터 이용 및 카드사용지역/업종/거주지역/성별/연령/생애주기/년/월/생활권 피쳐 사용
