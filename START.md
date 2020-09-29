# 나만의 분류도 

* 추천 시스템에서 사용하는 데이터의 특성
  * explicit data
    * item에 대한 user의 평가가 대소 비교가 가능한 수치로 주어진 데이터 (ordinal data)   
  * implicit data
    * item에 대한 user의 평가가 대소 뚜렷히 대소 비교가 가능한 형태로 주어지지 않은 경우
        * 예시) CTR (click through rate) , perchase / Non perchase 

  * explicit data 와 impliit data의 차이점 비교   
    * implicit의 경우 negatigve sample에 대한 판단이 어렵다. 
      * missing sample을 user-item interaction이 없는 데이터 샘플로 정의를 하였을 경우 
        * missing sample 에는 (unknown positive sample 즉 사용자가 item을 몰라서 구입하지 않았지만 선호하는 케이스) 와 (known & dislike case) 알지만 싫어하여 구입하지 않은 경우가 섞여 있다. 따라서 explicit에서 사용하는 방식과 유사하게 missing data를 모두 missing으로 처리해 버리면 one - class classfication 문제가 되어 버린다.
      * implicit의 경우 click / purchase를 하였다고 하더라도 user preference에 대한 확신이 어렵다 (confidence로 표현)
        * 단 한 번 구매했다고 좋아하는 걸까? / 단 한 번 click 했다고 좋아하는 걸까?
    * implicit data unknown data 처리 방식
      * missing - data를 전부 negative feedback으로 간주 하고 처리 한다. s
        * 이렇게 할 경우 학습 비효율 성이 나타남 (known, missing full data를 전부 고려해야해서)  --> online service에 어려움 초래
      * unknown data를 전부 missing으로 처리하고 0으로 값을 setting
        * -> 대표적인 방식이 one-class classification
        * 이러한 방식은 (lacking negative feedback) 심각한 bias를 초래 할 수 있다.
      * 따라서 missing data 혹은 observed data 안에서 실제 true positive(click했는데 실제로 user preference가 높은 것)와 true negative(click 안했는데 실제로 user dislike인 케이스)를 어떻게 적절하게 골라낼 것인지가 관건이다.

    * implicit data에 관련된 논문
      *   Collaborative Filtering for Implicit Feedback Datasets (Yifan Hu, 2017)
          *   논문에서 착안한 개념 
              *   preference / confidence
                  *   preference : Indicator variabl (click 횟수 | 구매 횟수 >0 or not)
                  *   confidence : $c_{ui} = 1 + $\alpha p_{ui} 