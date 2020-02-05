> 목차
> ---
> 1. [분석 요건에 대한 정의](predict_insolation.md#분석-요건에-대한-정의)
> 1. [학습](predict_insolation.md#학습)
>    1. 학습 데이터셋 추가
>         1. 데이터셋 정보 설정
>         1. 원격 클러스터 실행
>         1. 저장
>    1. 학습 모델 실행
>         1. 데이터셋 선택
>         1. 알고리즘 선택
>         1. 파이프라인 저장
>         1. Run
>    1. 실행 결과 확인
>         1. Training Result
>         1. Model Description
>         1. Spark ML code
>    1. 실행 이력 확인
> 1. [예측](predict_insolation.md#예측)
>     1. 테스트 데이터셋 추가
>         1. 데이터셋 정보 설정
>         1. 원격 클러스터 실행
>         1. 저장
>     1. 예측 모델 실행
>         1. 테스트 데이터셋 선택
>         1. 예측 모델 확인
>         1. 결과 데이터 설정
>     1. 결과 데이터 확인
>         1. 결과 데이터 통계 정보
>         1. 결과 데이터 다운로드

<br>

# 분석 요건에 대한 정의

> 기상청의 일사량 데이터를 기반으로 태양광의 적정 발전량을 예측한다
<br>

## 데이터 정보

<br>

- Dataset : 14일 전부터 시간별 일사량, 발전량 데이터

| column명 | column 설명 | Value Example |
|---|:---:|---|
| `id` | 특정일부터 +x hour | 0,1,2... |
| `power` | 발전량 | 7.056 |
| `insolation` | 일사량 | 0.09 |
| `insolation_2` | 일사량^2 | 0.0081 |

<br/>

# 학습

## 학습 데이터셋 추가

### 데이터셋 정보 설정

![](img/1_dataset/01.dataset.png)

1. `상단 메뉴 → DATASET`
1. `New` 버튼 클릭

ICOS에 저장된 데이터 파일을 선택한다.  
`ICOS` 선택 → `파일 불러오기` 버튼 클릭

![](img/1_dataset/02.newdataset.png)

<br>

학습에 사용할 데이터(`insolation_trainset.csv`)를 불러온다.

- Storage: `IBMOSC1146611-6`
- Bucket: `handson-bucket`
- 경로: `~/insolation_trainset.csv`

![](img/1_dataset/03.icos.png)

<br>

학습 데이터에 대한 정보를 입력한다.

- Dataset Name: `insolation_trainset`
- Header exists: `TRUE`
- Delimiter: `,`
- Description: `학습 데이터`

![](img/1_dataset/04.newdataset.png)

<br>

### 원격 클러스터 실행

원격 클러스터를 선택한다.

![](img/1_dataset/05.cluster.png)

<br>

### 저장

추가된 데이터셋을 목록에서 확인한다.

![](img/1_dataset/06.saved.png)

<br>

## 학습 모델 실행

워크스페이스 페이지로 이동한다.  
`상단 메뉴 → WORKSPACE`

![](img/2_train/01.workspace.png)

폴더 아이콘 버튼을 클릭한다.

### 데이터셋 선택

불러올 데이터셋의 `Apply` 버튼을 클릭한다.

![](img/2_train/02.apply.png)

### 알고리즘 선택

알고리즘 목록에서 **Linear Regressor**를 선택하고 parameter를 입력한다.

| Index | Parameter | Value Example |
|---|:---:|---|
| **1** | `input` | insolation,insolation_2 |
| **2** | `output` | predict |
| **3** | `label` | power |

![](img/2_train/03.lr.png)

### 파이프라인 실행

파이프라인 실행을 위해 `우측 상단 → Run` 버튼을 클릭하면  
클러스터, 생성할 모델, 결과 데이터셋 정보를 입력할 수 있는 창이 뜬다.  

먼저 클러스터 선택 버튼을 클릭한다.

![](img/2_train/06.run.png)

사용할 클러스터를 선택하고 실행 버튼을 클릭한다.

![](img/2_train/07.cluster.select.png)

모델 생성을 위해 모델을 저장하고 데이터셋은 생성하지 않고 파이프라인을 실행한다.

- Model 정보
    - Name : `insolation_LRmodel`
    - Description : `predict power from insolation using linear regressor`
    - Path : `~/insolation_LRmodel`

![](img/2_train/08.checkbox.png)

## 실행 결과 확인

실행이 완료 되면 `우측 상단 → Show results` 버튼을 클릭힌다.

![](img/2_train/10.showresult.png)

실행 결과로 다음 3가지 정보를 볼 수 있다.

- Training Result: `훈련 결과`
- Model Description: `모델 설명`
- Spark ML code: `코드로 변환된 ML Modeler`

### Training Result

**Regression Evaluator**

![](img/2_train/11.result1.png)

### Model Description

![](img/2_train/12.result2.png)

### Spark ML code

![](img/2_train/13.result3.png)

## 실행 이력 확인

`상단 메뉴 → TRAINING HISTORY`에서 현재까지 실행한 훈련 기록들을 확인한다.

![](img/2_train/14.history.png)

# 예측

## 테스트 데이터셋 추가

![](img/1_dataset/01.dataset.png)

1. `상단 메뉴 → DATASET`
1. `New` 버튼 클릭

### 데이터셋 정보 설정

1. `ICOS` 선택 → `파일 불러오기` 버튼 클릭
   - Storage: `IBMOSC1146611-6`
   - Bucket: `handson-bucket`
   - 경로: `~/insolation_testset.csv`
1. 정보 입력
   - Dataset Name: `insolation_testset`
   - Header exists: `TRUE`
   - Delimiter: `,`
   - Description: `테스트 데이터`

![](img/3_predict/03.dataset.png)

<br>

### 원격 클러스터 실행

원격 클러스터를 선택한다.

![](img/3_predict/04.cluster.png)

<br>

### 저장

추가된 데이터셋을 목록에서 확인한다.

![](img/3_predict/05.saved.png)

<br>

## 예측 모델 실행

이전에 생성한 모델을 이용해서 예측한다.

1. `상단 메뉴 → MODEL`
1. insolation_LRmodel 선택
1. `Predict` 버튼 클릭

![](img/3_predict/08.model.png)

<br>

Predict 창에서 `Select Dataset` 버튼을 클릭한다.

![](img/3_predict/09.predict.png)

<br>

### 테스트 데이터셋 선택

`insolation_testset` 데이터셋을 선택하고 `Confirm` 버튼 클릭한다.

![](img/3_predict/10.testset.png)

### 예측 모델 확인

테스트 데이터가 Scale과 Encode 과정을 거친 후 회귀 분석까지 이루어지는 과정을 확인한다.  
`Predict` 버튼을 클릭한다.

![](img/3_predict/11.predict.png)

### 결과 데이터 설정

예측 후에 저장할 결과 데이터 정보와 컬럼 정보를 설정한다.
`Save` 버튼 클릭하여 예측을 실행한다.  
예측 작업이 끝나면 닫기 버튼을 클릭한다.

- Dataset Info
   - Name: `insolation_LRmodel_result`
   - Description: `테스트 결과`
   - HDFS 경로: `/tmp/mlmodeler`
- Column List
   1. id
   1. power
   1. predict

![](img/3_predict/13.predict.png)

## 결과 데이터 확인

생성된 submssion 데이터셋을 확인한다.

1. `상단 메뉴 → DATASET`
1. `insolation_LRmodel_result` 클릭

![](img/3_predict/14.data.png)

### 결과 데이터 통계 정보

결과 데이터에 대해 간단한 통계 정보를 확인한다.

1. `predict: <DoubleType>` 선택
1. Statistics 버튼 클릭

![](img/3_predict/15.statistics.png)

### 결과 데이터 다운로드

데이터셋을 다운 받을 수 있다.

![](img/3_predict/16.download.png)

| id | power | predict |
|---|---|---|
| ... | ... | ... |
| 28 | 0 | 1.0481953533562658 |
| 29 | 0 | 1.0481953533562658 |
| 30 | 0.144 | 1.0481953533562658 |
| 31 | 77.04 | 37.83410271439635 |
| 32 | 324.936 | 269.41957845364976 |
| 33 | 508.248 | 481.4564154206275 |
| ... | ... | ... |


