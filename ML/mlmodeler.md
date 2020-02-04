
# ML modeler 알고리즘 사용법

> 목차
> ---
> 1. [알고리즘 목록](mlmodeler.md#알고리즘-목록)
> 1. [Parameter info](mlmodeler.md#Parameter-info)
> 1. [예제 및 시나리오](mlmodeler.md#예제-및-시나리오)

## 알고리즘 목록

[Transformer]  
[Binarizer](mlmodeler.md#Binarizer)  
[Bucketizer](mlmodeler.md#Bucketizer)  
[ChiSqSelector](mlmodeler.md#ChiSqSelector)  
[CountVectorizer](mlmodeler.md#CountVectorizer)  
[DCT](mlmodeler.md#DCT)  
[ElementwiseProduct](mlmodeler.md#ElementwiseProduct)  
[FeatureHasher](mlmodeler.md#FeatureHasher)  
[MaxAbsScaler](mlmodeler.md#MaxAbsScaler)  
[MinMaxScaler](mlmodeler.md#MinMaxScaler)  
[Normalizer](mlmodeler.md#Normalizer)  
[OneHotEncoder](mlmodeler.md#OneHotEncoder)  
[PCA](mlmodeler.md#PCA-(Principal-Component-Analysis))  
[QuantileDiscretizer](mlmodeler.md#QuantileDiscretizer)  
[StandardScaler](mlmodeler.md#StandardScaler)  
[Word2Vec](mlmodeler.md#Word2Vec)  

[Regression]  
[AFTSurvivalRegression](mlmodeler.md#AFTSurvivalRegression)  
[DecisionTreeRegressor](mlmodeler.md#DecisionTreeRegressor)  
[GBTRegressor](mlmodeler.md#GBTRegressor)  
[GeneralizedLinearRegression](mlmodeler.md#GeneralizedLinearRegression)  
[IsotonicRegression](mlmodeler.md#IsotonicRegression)  
[LinearRegression](mlmodeler.md#LinearRegression)  
[RandomForestRegressor](mlmodeler.md#RandomForestRegressor)  
[XGBoostRegressor](mlmodeler.md#XGBoostRegressor)  

[Recommendation]  
[ALS](mlmodeler.md#ALS)  

[Clustering]  
[BisectingKMeans](mlmodeler.md#BisectingKMeans)  
[GaussianMixture](mlmodeler.md#GaussianMixture)  
[KMeans](mlmodeler.md#KMeans)  
[LDA](mlmodeler.md#LDA)  

[classification]  
[DecisionTreeClassifier](mlmodeler.md#DecisionTreeClassifier)  
[GBTClassifier](mlmodeler.md#GBTClassifier)  
[LinearSVC](mlmodeler.md#LinearSVC)  
[LogisticRegression](mlmodeler.md#LogisticRegression)  
[MultilayerPerceptionClassifier](mlmodeler.md#MultilayerPerceptionClassifier)  
[NaiveBayes](mlmodeler.md#NaiveBayes)  
[OneVsRest](mlmodeler.md#OneVsRest)  
[RandomForestClassifier](mlmodeler.md#RandomForestClassifier)  
[XGBoostClassifier](mlmodeler.md#XGBoostClassifier)  

<br/><br/>

## Parameter info

### Binarizer
- 연속적인 변수를 이진 변수로 변환

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | combobox | feature |
| **2** | `output` | String | binarized |
| 3 | `threshold` | Double | 0.0 |

[예제](mlmodeler.md#Binarizer-예제)

### Bucketizer 
- 연속적인 변수를 임계치의 리스트를 기반으로 쪼개어 범위별로 변환

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | feature1,feature2 |
| **2** | `output` | String | bucketized1,bucketized2 |
| **3** | `splits` | String | 0,0.5,1.0 |

[예제](mlmodeler.md#Bucketizer-예제)

### ChiSqSelector  
- 카이제곱 검정을 통해 타깃의 분산을 가장 잘 나타내는 n개의 카테고리 변수들을 선택

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | atemp |
| **3** | `label` | combobox | season |
| 4 | `numTop` | Integer | 50 |

[예제](mlmodeler.md#ChiSqSelector-예제)

### CountVectorizer  
- 문장의 특징이 되는 단어들의 빈도를 가중치로 벡터 생성

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | combobox | year |
| **2** | `output` | String | predict |
| 3 | `tokenizerPattern` | String | \\ |
| 4 | `vocabSize` | Integer | 262144 |
| 5 | `minDF` | Double | 1.0 |
| 6 | `minTF` | Double | 1.0 |
| 7 | `binary` | combobox | false |

[예제](mlmodeler.md#CountVectorizer-예제)

### DCT(Discrete Cosine Transform)  
- 실수로 이루어진 벡터를 입력받아 같은 길이의 다른 빈도의 벡터를 리턴

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | atemp |
| 3 | `inverse` | combobox | season |

[예제](mlmodeler.md#DCT-예제)

### ElementwiseProduct  
- 벡터 * scale

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | atemp |
| **3** | `scaleVect` | String | season |

[예제](mlmodeler.md#ElementwiseProduct-예제)

### FeatureHasher  
- 해싱함수를 사용하여 각 단어를 고정 크기 벡터의 인덱스에 매핑

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | atemp |

[예제](mlmodeler.md#FeatureHasher-예제)

### MaxAbsScaler  
- 데이터의 범위를 [-1.0, 1.0] 사이로 재조정

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | atemp |

[예제](mlmodeler.md#MaxAbsScaler-예제)

### MinMaxScaler  
- 데이터의 범위를 재조정

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | scaled |
| 3 | `min` | Double | 0.0 |
| 4 | `max` | Double | 1.0 |

[예제](mlmodeler.md#MinMaxScaler-예제)

### Normalizer  
- p-norm 값을 이용해 데이터를 단위 크기로 조정

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | year |
| **2** | `output` | String | encoded |
| 3 | `p` | Integer | 2 |

[예제](mlmodeler.md#Normalizer-예제)

### OneHotEncoder
- 카테고리 칼럼을 이진 벡터 칼럼으로 인코딩

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | year |
| **2** | `output` | String | encoded |
| 3 | `dropLast` | Boolean | true |

[예제](mlmodeler.md#OneHotEncoder-예제)

### PCA (Principal Component Analysis)
- 데이터의 분산을 최대한 보존하는 축을 찾아 데이터 축소

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | year |
| **2** | `output` | String | encoded |
| **3** | `k` | Integer | 4 |

[예제](mlmodeler.md#PCA-예제)

### QuantileDiscretizer  
- 백분위수를 기준으로 데이터 분할

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | year |
| **2** | `output` | String | encoded |
| 3 | `numBuckets` | Integer | 2 |

[예제](mlmodeler.md#QuantileDiscretizer-예제)

### StandardScaler  
- 각 feature의 평균을 0, 분산을 1로 변경

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | temperature,humididy |
| **2** | `output` | String | atemp |
| 3 | `withStd` | Boolean | true |
| 4 | `withMean` | Boolean | false |

[예제](mlmodeler.md#StandardScaler-예제)

### Word2Vec  
- 스트링 문장을 고정된 크기의 벡터 형태로 변환

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | combobox | text |
| **2** | `output` | String | result |
| 3 | `tokenizerPattern` | String | \\ |
| 4 | `vectorSize` | Integer | 100 |
| 5 | `windowSize` | Integer | 5 |
| 6 | `minCount` | Integer | 5 |
| 7 | `maxSentenceLength` | Integer | 1000 |
| 8 | `numPartitions` | Integer | 1 |
| 9 | `stepSize` | Double | 0.025 |
| 10 | `maxIter` | Integer | 1 |
| 11 | `seed` | seed | 123L |

[예제](mlmodeler.md#Word2Vec-예제)

### AFTSurvivalRegression  
- 한 Feature의 작은 효과가 기대 수명을 증가시키거나 감소시킬 수 있다는 것을 가정한 매개 변수 모델

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `featureindex` | Integer | 0 |
| 7 | `fitintercept` | Boolean | true |
| 8 | `censor` | Integer | 1 |
| 9 | `toler` | Double | 0.000001 |
| 10 | `maxIter` | Integer | 100 |
| 11 | `validationSetPath` | path | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#AFTSurvivalRegression-시나리오)

### DecisionTreeRegressor  
- 결정 트리 분류 모델과 비슷하나 레이블이 이진 데이터가 아니라 연속적인 데이터이거나 여러 개의 레이블을 가지는 데이터

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `maxCategory` | Integer | 20 |
| 7 | `impurity` | combobox | variance |
| 8 | `maxBins` | Integer | 32 |
| 9 | `maxDepth` | Integer | 5 |
| 10 | `seed` | seed | 1234L |
| 11 | `validationSetPath` | path | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#DecisionTreeRegressor-시나리오)

### GBTRegressor  
- 여러 개의 약한 모델들을 뭉쳐서 강한 모델을 만들어내는 앙상블 모델

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `maxCategory` | Integer | 20 |
| 7 | `impurity` | combobox | variance |
| 8 | `lossType` | combobox | squared |
| 9 | `maxBins` | Integer | 32 |
| 10 | `maxDepth` | Integer | 5 |
| 11 | `maxIter` | Integer | 20 |
| 12 | `seed` | seed | 1234L |
| 13 | `stepSize` | Double | 0.1 |
| 14 | `subSamplingRate` | Double | 1.0 |
| 15 | `validationSetPath` | path | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#GBTRegressor-시나리오)

### GeneralizedLinearRegression  
- 다른 커널 함수를 사용하는 선형 모델

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `family` | combobox | gaussian |
| 7 | `intercept` | Boolean | true |
| 8 | `solver` | combobox | irls |
| 9 | `toler` | Double | 0.000001 |
| 10 | `maxIter` | Integer | 100 |
| 11 | `regParam` | Double | 0.0 |
| 12 | `validationSetPath` | path | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#GeneralizedLinearRegression-시나리오)

### IsotonicRegression  
- 감소하지 않는 자유로운 형태의 데이터에 대한 회귀 모델

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `featureindex` | Integer | 0 |
| 7 | `isotonic` | Boolean | true |
| 8 | `validationSetPath` | path | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#IsotonicRegression-시나리오)

### LinearRegression  
- 피처들 사이의 관계가 선형이고 레이블이 연속적인 값이며 오차가 정규 분포를 띈다는 것을 가정한 모델

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `elasticNet` | Double | 0.0 |
| 7 | `intercept` | Boolean | true |
| 8 | `solver` | combobox | auto |
| 9 | `std` | Boolean | true |
| 10 | `toler` | Double | 0.000001 |
| 11 | `maxIter` | Integer | 100 |
| 12 | `regParam` | Double | 0.0 |
| 13 | `validationSetPath` | DatasetPath | s3a://handson-bucket/ML/test.csv |

[시나리오](mlmodeler.md#LinearRegression-시나리오)

### RandomForestRegressor  
- 분리된 값이 아닌 연속적인 값들에 대해 학습

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | combobox | year |
| **2** | `output` | String | predict |
| **3** | `label` | combobox | count |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `maxCategory` | Integer | 20 |
| 7 | `impurity` | combobox | variance |
| 8 | `maxBins` | Integer | 32 |
| 9 | `maxDepth` | Integer | 5 |
| 10 | `numTrees` | Integer | 20 |
| 11 | `seed` | seed | 123L |
| 12 | `subSamplingRate` | Double | 1.0 |
| 13 | `strategy` | combobox | auto |
| 14 | `validationSetPath` | DatasetPath | s3a://handson-bucket/ML/test.csv |

[시나리오](mlmodeler.md#RandomForestRegressor-시나리오)

### XGBoostRegressor   
- 

[시나리오](mlmodeler.md#XGBoostRegressor-시나리오)

### ALS   
- 

[시나리오](mlmodeler.md#ALS-시나리오)

### BisectingKMeans  
- 계층적 군집화와 K-평균 군집화 알고리즘의 조합

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `maxIter` | Integer | 20 |
| 4 | `seed` | seed | 1234 |
| 5 | `minDiv` | Double | 1.0 |
| 6 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#BisectingKMeans-시나리오)

### GaussianMixture  
- k 가우시안 분포를 알려지지 않은 파라미터와 같이 사용

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `k` | Integer | 2 |
| 4 | `maxIter` | Integer | 10 |
| 5 | `seed` | seed | 1234 |
| 6 | `toler` | Double | 0.0001 |
| 7 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#GaussianMixture-시나리오)

### KMeans  
- 각 데이터와 군집 사이 거리 제곱의 합을 최소화하는 중심을 반복적으로 계산하면서 가장 최적화된 K개의 중심을 찾아가는 모델

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `initMode` | combobox | k-means|| |
| 4 | `initSteps` | Integer | 5 |
| 5 | `k` | Integer | 2 |
| 6 | `maxIter` | Integer | 20 |
| 7 | `seed` | seed | 1234 |
| 8 | `toler` | Double | 0.0001 |
| 9 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#KMeans-시나리오)

### LDA
- 자연어 처리 토픽 모델링에 사용

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| **1** | `input` | checkbox | c1,c2 |
| **2** | `output` | String | result |
| 3 | `k` | Integer | 2 |
| 4 | `maxIter` | Integer | 20 |
| 5 | `seed` | seed | 1234L |
| 6 | `checkpointInterval` | Integer | 10 |
| 7 | `optimizer` | combobox | online |
| 8 | `subsamplingRate` | Double | 0.05 |
| 9 | `topicConcentration` | Double | 1.1 |
| 10 | `keepLastCheckpoint` | Boolean | true |
| 11 | `learningDecay` | Double | 0.51 |
| 12 | `learningOffset` | Integer | 1024 |
| 13 | `optimizeDocConcentration` | Boolean | false |
| 14 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#LDA-시나리오)

### DecisionTreeClassifier  
- 관찰된 데이터에 대한 클래스를 예측하는 결정 트리 모델을 생성

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `automodel` | Boolean | false |
| 2 | `input` | checkbox | c1,c2 |
| 3 | `output` | String | result |
| 4 | `label` | combobox | c0 |
| 5 | `splitWeight` | Double | 0.7 |
| 6 | `splitSeed` | seed | 1234L |
| 7 | `maxCategory` | Integer | 20 |
| 8 | `impurity` | combobox | gini |
| 9 | `maxBins` | Integer | 32 |
| 10 | `maxDepth` | Integer | 5 |
| 11 | `seed` | seed | 1234L |
| 12 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#DecisionTreeClassifier-시나리오)

### GBTClassifier  
- DecisionTreeRegressor에서처럼 레이블 타입만 다름

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `automodel` | Boolean | false |
| 2 | `input` | checkbox | c1,c2 |
| 3 | `output` | String | result |
| 4 | `label` | combobox | c0 |
| 5 | `splitWeight` | Double | 0.7 |
| 6 | `splitSeed` | seed | 1234L |
| 7 | `maxCategory` | Integer | 20 |
| 8 | `impurity` | combobox | entropy |
| 9 | `lossType` | combobox | logistic |
| 10 | `maxBins` | Integer | 32 |
| 11 | `maxDepth` | Integer | 5 |
| 12 | `maxIter` | Integer | 20 |
| 13 | `seed` | seed | 1234L |
| 14 | `stepSize` | Double | 0.1 |
| 15 | `subSamplingRate` | Double | 1.0 |
| 16 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#GBTClassifier-시나리오)

### LinearSVC  
- 

[시나리오](mlmodeler.md#LinearSVC-시나리오)

### LogisticRegression  
- 데이터가 특정 클래스로 속하는 확률 계산

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `automodel` | Boolean | false |
| 2 | `input` | checkbox | c1,c2 |
| 3 | `output` | String | result |
| 4 | `label` | combobox | c0 |
| 5 | `splitWeight` | Double | 0.7 |
| 6 | `splitSeed` | seed | 1234L |
| 7 | `elasticNet` | Double | 0.0 |
| 8 | `intercept` | Boolean | true |
| 9 | `threshold` | Double | 0.5 |
| 10 | `std` | Boolean | true |
| 11 | `toler` | Double | 0.00001 |
| 12 | `maxIter` | Integer | 100 |
| 13 | `regParam` | Double | 0.3 |
| 16 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#LogisticRegression-시나리오)

### MultilayerPerceptionClassifier  
- 최소한 세 개의 완벽하게 연결된 인공신경망(모델 객체를 생성할 때 명시해줘야 하는 파라미터)을 가짐

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `input` | checkbox | c1,c2 |
| 2 | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `layers` | no. of layers | 2,1,1 |
| 7 | `maxIter` | Integer | 100 |
| 8 | `seed` | seed | 1234 |
| 9 | `stepSize` | Double | 0.03 |
| 10 | `toler` | Double | 0.00001 |
| 11 | `solver` | combobox | l-bfgs |
| 12 | `blockSize` | Integer | 128 |
| 13 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#MultilayerPerceptionClassifier-시나리오)

### NaiveBayes  
- 베이즈 이론을 기반으로 데이터를 분류하기 위해 조건부 확률을 사용

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `input` | checkbox | c1,c2 |
| 2 | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `smoothing` | Double | 1.0 |
| 7 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#NaiveBayes-시나리오)

### OneVsRest  
- 여러 클래스에 대한 분류를 이진 분류로 축소

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `input` | checkbox | c1,c2 |
| 2 | `output` | String | result |
| 3 | `label` | combobox | c0 |
| 4 | `splitWeight` | Double | 0.7 |
| 5 | `splitSeed` | seed | 1234L |
| 6 | `elasticNet` | Double | 0.0 |
| 7 | `intercept` | Boolean | true |
| 8 | `threshold` | Double | 0.5 |
| 9 | `std` | Boolean | true |
| 10 | `toler` | Double | 0.00001 |
| 11 | `maxIter` | Integer | 100 |
| 12 | `regParam` | Double | 0.0 |
| 13 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#OneVsRest-시나리오)

### RandomForestClassifier  
- 여러 개의 결정 트리를 만들고, 그 결정 트리들의 결과들을 예측 값으로 사용

| Index | Parameter | Type | Value Example |
|---|:---:|:---:|---|
| 1 | `automodel` | Boolean | false |
| 2 | `input` | checkbox | c1,c2 |
| 3 | `output` | String | result |
| 4 | `label` | combobox | c0 |
| 5 | `splitWeight` | Double | 0.7 |
| 6 | `splitSeed` | seed | 1234L |
| 7 | `maxCategory` | Integer | 20 |
| 8 | `impurity` | combobox | gini |
| 9 | `maxBins` | Integer | 32 |
| 10 | `maxDepth` | Integer | 5 |
| 11 | `numTrees` | Integer | 20 |
| 12 | `seed` | seed | 1234L |
| 13 | `subSamplingRate` | Double | 1.0 |
| 14 | `strategy` | combobox | auto |
| 15 | `threshold` | Double | 0.5 |
| 16 | `validationSetPath` | DatasetPath | /tmp/validationSet.csv |

[시나리오](mlmodeler.md#RandomForestClassifier-시나리오)

### XGBoostClassifier
- 

[시나리오](mlmodeler.md#XGBoostClassifier-시나리오)


<br/><br/>

## 예제 및 시나리오

### Binarizer 예제

- input data  

| Index | feature |
|---|:---:|
| 1 | 0.1 |
| 2 | 0.8 |
| 3 | 0.5 |
| 4 | 0.51 |
| 5 | 0.511 |

<br>

- parameter setting  

| Index | Parameter | Value Example |
|---|:---:|---|
| **1** | `input` | feature |
| **2** | `output` | binarized_feature |
| 3 | `threshold` | 0.51 |

<br>

- output data  

| Index | feature | binarized_feature |
|---|:---:|---|
| 1 | 0.1 | 0.0 |
| 2 | 0.8 | 1.0 |
| 3 | 0.5 | 0.0 |
| 4 | 0.51 | 0.0 |
| 5 | 0.511 | 1.0 |

<br>

### Bucketizer 예제

- input data  

| Index | feature1 | feature2 |
|---|:---:|---|
| 1 | -1.0 | 0.1 |
| 2 | -0.5 | -0.5 |
| 3 | 0.0 | -0.1 |
| 4 | 0.3 | 0.5 |
| 5 | 1.0 | 0.6 |

<br>

- parameter setting  

| Index | Parameter | Value Example |
|---|:---:|---|
| **1** | `input` | feature1,feature2 |
| **2** | `output` | bucketedFeature1,bucketedFeature2 |
| **3** | `splits` | -1.0,0.0,1.0 |

<br>

- output data  

| Index | feature1 | feature2 | bucketedFeature1 | bucketedFeature2 |
|---|:---:|:---:|:---:|---|
| 1 | -1.0 | 0.1 | 1.0 | 1.0 |
| 2 | -0.5 | -0.5 | 0.0 | 0.0 |
| 3 | 0.0 | -0.1 | 1.0 | 0.0 |
| 4 | 0.3 | 0.5 | 1.0 | 1.0 |
| 5 | 1.0 | 0.6 | 0.0 | 1.0 |

<br>

### ChiSqSelector 예제

- input data

| Index | Feature1 | Feature2 | Feature3 | Label |
|---|---|---|---|---|
| 1 | 1.0 | 2.0 | 3.0 | 2.0 |
| 2 | 2.0 | 5.0 | 6.0 | 2.0 |
| 3 | 2.0 | 8.0 | 9.0 | 1.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | Feature1,Feature2,Feature3 |
| 2 | `output` | selectedFeature |
| 3 | `label` | Label |
| 4 | `numTop` | 1 |

<br>

- output data

| Index | Feature1 | Feature2 | Feature3 | Label | selectedFeature |
|---|---|---|---|---|---|
| 1 | 1.0 | 2.0 | 3.0 | 2.0 | 2.0 |
| 2 | 2.0 | 5.0 | 6.0 | 2.0 | 5.0 |
| 3 | 2.0 | 8.0 | 9.0 | 1.0 | 8.0 |

<br>

### CountVectorizer 예제

- input data

| id | words |
|---|:---:|
| 0 | a\\\\b\\\\c |
| 1 | a\\\\b\\\\b\\\\c\\\\a |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | words |
| 2 | `output` | features |
| 3 | `tokenizerPattern` | \\\\ |
| 4 | `vocabSize` | 3 |
| 5 | `minDF` | 2.0 |
| 6 | `minTF` | 1.0 |
| 7 | `binary` | false |

<br>

- output data

| id | words | features |
|---|:---:|---|
| 0 | a\\\\b\\\\c | (3,[0,1,2],[1.0,1.0,1.0]) |
| 1 | a\\\\b\\\\b\\\\\\c\\\\a | (3,[0,1,2],[2.0,2.0,1.0]) |

<br>

### DCT 예제

- input data

| Index | Feature1 | Feature2 |
|---|:---:|---|
| 1 | 0.0 | 1.0 |
| 2 | -1.0 | 2.0 |
| 3 | 14.0 | -2.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | Feature1,Feature2 |
| 2 | `output` | FeatureDCT |
| 3 | `inverse` | False |

<br>

- output data

| Index | Feature1 | Feature2 | FeatureDCT |
|---|:---:|---|---|
| 1 | 0.0 | 1.0 | (2, [0,1], [0.7071, -0.7071]) |
| 2 | -1.0 | 2.0 | (2, [0,1], [0.7071, -2.1213]) |
| 3 | 14.0 | -2.0 | (2, [0,1], [8.4853, 11.3137]) |

<br>

### ElementwiseProduct 예제

- input data

| Index | Vector1 | Vector2 |
|---|:---:|---|
| 1 | 3.0 | 1.0 |
| 2 | -1.0 | 2.0 |
| 3 | 14.0 | -2.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | Vector1,Vector2 |
| 2 | `output` | transformedVector |
| 3 | `scaleVect` | 2.0,1.0 |

<br>

- output data

| Index | Vector1 | Vector2 | transformedVector |
|---|:---:|---|---|
| 1 | 0.0 | 1.0 | (2, [0,1], [6.0, 1.0]) |
| 2 | -1.0 | 2.0 | (2, [0,1], [-2.0,2.0]) |
| 3 | 14.0 | -2.0 | (2, [0,1], [28.0, -2.0]) |

<br>

### FeatureHasher 예제

- input data

| real | bool | stringNum | string
|---|---|---|---|
| 2.2 | true | 1 | foo |
| 3.3 | false | 2 | bar |
| 4.4 | false | 3 | baz |
| 5.5 | false | 4 | foo |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| **1** | `input` | real,bool,stringNum,string |
| **2** | `output` | feature |

<br>

- output data

| real | bool | stringNum | string | feature |
|---|---|---|---|---|
| 2.2 | true | 1 | foo | (262144,[51871, 63643,174475,253195],[1.0,1.0,2.2,1.0]) |
| 3.3 | false | 2 | bar | (262144,[6031,  80619,140467,174475],[1.0,1.0,1.0,3.3]) |
| 4.4 | false | 3 | baz | (262144,[24279,140467,174475,196810],[1.0,1.0,4.4,1.0]) |
| 5.5 | false | 4 | foo | (262144,[63643,140467,168512,174475],[1.0,1.0,1.0,5.5]) |

<br>

### MaxAbsScaler 예제

- input data

| feature1 | feature2 | feature3 |
|---|---|---|
| 1.0 | 0.1 | -8.0 |
| 2.0 | 1.0 | -4.0 |
| 4.0 | 10.0 | 8.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| **1** | `input` | feature1,feature2,feature3 |
| **2** | `output` | scaledFeatures |

<br>

- output data

| feature1 | feature2 | feature3 | scaledFeatures |
|---|---|---|---|
| 1.0 | 0.1 | -8.0 | [0.25,0.010000000000000002,-1.0] |
| 2.0 | 1.0 | -4.0 | [0.5,0.1,-0.5] |
| 4.0 | 10.0 | 8.0 | [1.0,1.0,1.0] |

<br>

### MinMaxScaler 예제

- input data

| feature1 | feature2 |
|---|---|
| 0.0 | 0.0 |
| 0.449641 | 0.202177 |
| 1.114602 | 1.242338 |
| 0.670564 | 0.449656 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | feature1,feature2 |
| 2 | `output` | scaledFeature |
| 3 | `min` | -1.0 |
| 4 | `max` | 4.0 |

<br>

- output data

| feature1 | feature2 | scaledFeature |
|---|---|---|
| 0.0 | 0.0 | (2,[0,1],[-1.0,-1.0]) |
| 0.449641 | 0.202177 | (2,[0,1],[1.017048,-0.186303]) |
| 1.114602 | 1.242338 | (2,[0,1],[4.0,4.0]) |
| 0.670564 | 0.449656 | (2,[0,1],[2.008088,0.809719]) |

<br>

[시나리오](mlmodeler.md#시나리오)

<br>

### Normalizer 예제

- input data

| feature1 | feature2 |
|---|---|
| 1.0 | 0.5 |
| 2.0 | -1.0 |
| 4.0 | 10.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | feature1,feature2 |
| 2 | `output` | normFeature |
| 3 | `p` | 2 |

<br>

- output data

| feature1 | feature2 | normFeature |
|---|---|---|
| 1.0 | 0.5 | [0.894427,0.447213] |
| 2.0 | -1.0 | [0.894427,-0.447213] |
| 4.0 | 10.0 | [0.371390,0.928476] |

<br>

### OneHotEncoder 예제

- input data

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | year |
| 2 | `output` | encoded |
| 3 | `dropLast` | true |

<br>

- output data

<br>

### PCA 예제

- input data

| f1 | f2 | f3 | f4 |
|---|---|---|---|
| 3.0 | 0.0 | 2.0 | 5.0 |
| 1.0 | 6.0 | 7.0 | 0.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | f1,f2,f3,f4 |
| 2 | `output` | pcaFeature |
| 3 | `k` | 3 |

<br>

- output data

| f1 | f2 | f3 | f4 | pcaFeature |
|---|---|---|---|---|
| 3.0 | 0.0 | 2.0 | 5.0 | [-2.213594,-0.266422,2.920448] |
| 1.0 | 6.0 | 7.0 | 0.0 | [7.273238,-0.266422,2.920448] |

<br>

### QuantileDiscretizer 예제

- input data

| id | hour | hour2 |
|---|---|---|
| 0 | 18.0 | 0.0 |
| 1 | 19.0 | 10.0 |
| 2 | 8.0 | 5.5 |
| 3 | 5.0 | 3.0 |
| 4 | 2.2 | 1.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | hour1,hour2 |
| 2 | `output` | result1,result2 |
| 3 | `numBuckets` | 3 |

<br>

- output data

| id | hour | hour2 | result1 | result2 |
|---|---|---|---|---|
| 0 | 18.0 | 0.0 | 2.0 | 0.0 |
| 1 | 19.0 | 10.0 | 2.0 | 2.0 |
| 2 | 8.0 | 5.5 | 1.0 | 2.0 |
| 3 | 5.0 | 3.0 | 1.0 | 1.0 |
| 4 | 2.2 | 1.0 | 0.0 | 1.0 |

<br>

### StandardScaler 예제

- input data

| id | feature1 | feature2 |
|---|---|---|
| 0 | -1.0 | 2.0 |
| 1 | 0.5 | 1.0 |
| 2 | 4.0 | 1.5 |
| 3 | 2.2 | -3.0 |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | feature1,feature2 |
| 2 | `output` | scaledFeature |
| 3 | `withStd` | true |
| 4 | `withMean` | false |

<br>

- output data

| id | feature1 | feature2 | scaledFeature |
|---|---|---|---|
| 0 | -1.0 | 2.0 | [-0.463448,0.874608] |
| 1 | 0.5 | 1.0 | [0.231724,0.437304] |
| 2 | 4.0 | 1.5 | [1.853793,0.655956] |
| 3 | 2.2 | -3.0 | [1.0195862,-1.311912] |

<br>

### Word2Vec 예제

- input data

| text |
|---|
| Hi I heard, about Spark |
| I wish Java could use case classes |
| Logistic regression models are neat |

<br>

- parameter setting

| Index | Parameter | Value Example |
|---|:---:|---|
| 1 | `input` | test |
| 2 | `output` | result |
| 3 | `tokenizerPattern` | " " |
| 4 | `vectorSize` | 3 |
| 5 | `windowSize` | 5 |
| 6 | `minCount` | 0 |
| 7 | `maxSentenceLength` | 1000 |
| 8 | `numPartitions` | 1 |
| 9 | `stepSize` | 0.025 |
| 10 | `maxIter` | 1 |
| 11 | `seed` | None |

<br>

- output data

| text | result |
|---|---|
| Hi I heard about Spark | [-0.005686,0.051667,-0.048950] |
| I wish Java could use case classes |  [-0.076057,0.107781,0.044006] |
| Logistic regression models are neat | [0.0443514,-0.047510,0.020748] |

<br>

### AFTSurvivalRegression 시나리오

[시나리오](predict_isolation.md)

### DecisionTreeRegressor 시나리오

[시나리오](predict_isolation.md)

### GBTRegressor 시나리오

[시나리오](predict_isolation.md)

### GeneralizedLinearRegression 시나리오

[시나리오](predict_isolation.md)

### IsotonicRegression 시나리오

[시나리오](predict_isolation.md)

### LinearRegression 시나리오

[시나리오](insolation_LR.md)

### RandomForestRegressor 시나리오

[시나리오](predict_isolation.md)

### XGBoostRegressor 시나리오

[시나리오](predict_isolation.md)

### ALS 시나리오

[시나리오](predict_isolation.md)

### BisectingKMeans 시나리오

[시나리오](predict_isolation.md)

### GaussianMixture 시나리오

[시나리오](predict_isolation.md)

### KMeans 시나리오

[시나리오](predict_isolation.md)

### LDA 시나리오

[시나리오](predict_isolation.md)

### DecisionTreeClassifier 시나리오

[시나리오](predict_isolation.md)

### GBTClassifier 시나리오

[시나리오](predict_isolation.md)

### LinearSVC 시나리오

[시나리오](predict_isolation.md)

### LogisticRegression 시나리오

[시나리오](predict_isolation.md)

### MultilayerPerceptionClassifier 시나리오

[시나리오](predict_isolation.md)

### NaiveBayes 시나리오

[시나리오](predict_isolation.md)

### OneVsRest 시나리오

[시나리오](predict_isolation.md)

### RandomForestClassifier 시나리오

[시나리오](predict_isolation.md)

### XGBoostClassifier 시나리오

[시나리오](predict_isolation.md)


