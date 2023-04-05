# thread_db
- 생분해성 섬유 물성 예측 모델 개발
- 역할
  - 이상치/결측치 처리된 data용 DB 설계 및 구축
 
> 기술 스택
> > MongoDB : 중급 <br>
> > Python  : 고급
> > Python.Pandas  : 고급 <br>
> > Python.Numpy   : 고급

## 실행 과정
0. 'thread_DB/MongoDB_Project/thread_data.ipynb'에서 필요 패키지/툴 설치
- `pip install pymongo`
- `pip install pandas`
  - 더 빠른 속도를 위해 pandas.modin 추천
- `pip install numpy`

1. `Preprocessing` class 실행
- 데이터 전처리/후처리를 위한 객체<br>
  i)    pivot_PET Method : 추출한 feature 명 재설정<br>
  ii)   distinction Method : ‘시료번호’와 ‘접수번호No.’를 기준으로 행에 대한 중복 제거 (약 2배수로 삭제)<br>
  iii)  compound_dye Method : 배합 염료 관련 features 추출<br>
  iv)   compound_prescription Method : 배합 조제 관련 features 추출<br>
  v)    post_processing Method : 조제 관련 data 후처리<br>
  vi)   pre_processing Method : 조제 관련 data 전처리<br>
  vii)  combine Method : 추출했던 features에 대한 data를 새로운 df형태로 추출<br><br>
  
2. `Raw` class 실행
- 데이터 수집 및 데이터베이스 관리를 담당하는 객체<br>
  i)    \__init\__ Method : 데이터베이스 연결<br>
  ii)   DataTuning Method : 원본 데이터의 경로와 원본 데이터의 이름을 매개변수로 df 형태로 추출<br>
  iii)  toJSON Method : df 형태로 추출된 데이터를 JSON 형태로 변환<br>
  iv)   insertDB Method : data를 DB에 삽입하는 과정 (삽입 이전/삽입 이후 데이터 개수 출력)<br>
  v)    read Method : 탐색하려는 feature와 최대 조회하려는 데이터 수를 매개변수로 각각 받음<br>
    - 각각 Raw, Preprocessed data Method 존재<br>
    
3. `RenameRAW` class 실행<br>
  i)    rename Method : feature 중복을 피하기 위해 '대분류_feature명' 형식으로 변환하는 객체<br>
  
4. 삽입 예시 (trial)

> 산학과제로 진행중인 프로젝트라 Raw data 공개가 불가능하므로 코드만 올려놓음
