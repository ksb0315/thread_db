# thread_db
- 생분해성 섬유 물성 예측 모델 개발
- 역할
  - 이상치/결측치 처리된 data용 DB 설계 및 구축
 
> 기술 스택
> > MongoDB : 중급 <br>
> > Python  : 고급 <br>
> > Python.Pandas  : 고급 <br>
> > Python.Numpy   : 고급 <br>
> > sklearn : 중급

## 실행 과정
0. 'thread_DB/MongoDB_Project/thread_data.ipynb'에서 필요 패키지/툴 설치
- `pip install scikit-learn`
- `pip install pymongo`
- `pip install pandas`
  - 더 빠른 속도를 위해 pandas.modin 추천
- `pip install numpy`

1. 간단한 데이터 전처리 (to DataFrame) 및 데이터베이스 삽입
- 데이터 전처리 진행
- 데이터베이스에 삽입
- 경로설정(`p`변수) 확인필요
  
2. 이상치 처리 기법 - Isolation Forest
- tree 구조로 데이터의 고립 정도를 파악하여 이상치 판별
    
3. 이상치 처리 기법 - IQR with boxplot
- 정규분포 데이터로 IQR(Q3-Q1)을 구해 오차범위와 신뢰구간을 구하는 이상치 판별법

> 산학과제로 진행중인 프로젝트라 Raw data 공개가 불가능하므로 코드만 올려놓음
