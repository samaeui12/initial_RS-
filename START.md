# 나만의 분류도 

* 추천 시스템에서 사용하는 데이터의 특성
  * explicit data
    * item에 대한 user의 평가가 대소 비교가 가능한 수치로 주어진 데이터 (ordinal data)   
  * implicit data
    * item에 대한 user의 평가가 대소 뚜렷히 대소 비교가 가능한 형태로 주어지지 않은 경우
        * 예시) CTR (click through rate) , perchase / Non perchase 

  * explicit data 와 impliit data의 차이점 비교   
    * impliit의 경우 negatigve sample에 대한 판단이 어렵다. 
      * missing sample을 user-item interaction이 없는 데이터 샘플로 정의를 하였을 경우 
        * possitive