# 다중 CCTV 객체추적 시스템 - CCTV Chaser

팀장 : 김병철   
팀원 : 박형민, 서주영, 위재원, 이명원

## 아이디어 개요    

   
      

### 1. 다중 CCTV 객체추적 시스템
>1) 지리정보시스템과 연계하여 CCTV를 지도에 등록
>2) CCTV에서 용의자를 객체처리(마우스 드래그 박스형식)
>3) 주위의 CCTV에서 객체를 추적해 용의자의 경로를 파악하는 시스템
### 2. 법보행 분석
>1) 수사관이 다중 CCTV 객체추적 시스템 활용
>2) 추적 데이터를 바탕으로 법보행 분석 데이터 확보
>3) 더욱 정확한 법보행 분석 모델

## 기존 시스템의 문제점

![수사기존방식](https://user-images.githubusercontent.com/41908146/91866598-a7fb8f00-ecad-11ea-8c59-a86bfa17f3ba.png)

### 1. 현재의 경찰의 CCTV를 활용한 용의자 추적 방법의 문제   
현재 경찰이 범인을 특정하기 위해서는 현장 CCTV를 하나하나 분석하면서 범인의 이동경로를 추적해야 한다.   이는 다양한 문제를 발생시키는데 먼저 범인
을 추적하는 시간이 필요 이상으로 소요된다.   

![개선시스템](https://user-images.githubusercontent.com/41908146/91866690-bf3a7c80-ecad-11ea-8f18-2ef26b37a9c1.png)

### 2. 개선된 방식 – 다중 CCTV 추적 시스템   

우리가 제안하고 싶은 경찰의 CCTV 활용 개선 방안은 ‘Real-time Detector인 CenterNet 알고리즘을 활용한 CCTV 영상 분석 자동화 시스템’이다. 이 시스템은 위 그림에 나온 것처럼 수사관이 한 CCTV에서 추적할 객체를 박스로 지정해주면 CenterNet 알고리즘을 활용하여 객체를 추적한다.

![시스템 구성도](https://user-images.githubusercontent.com/41908146/91866805-dbd6b480-ecad-11ea-89e8-9676ba2e030a.png)

### < 대략적인 전체 시스템 구성도 >   
추적 시스템의 인터페이스는 편리한 동선 파악을 위해 지도데이터 위에 구현되고 빠른 분석과 비용효율을 위해 2개의 데이터베이스와 2개의 서버를 사용하여 서버에서 고사양의 GPU를 사용하여 빠른 영상분석을 지원하는 시스템을 사용해야 한다고 생각한다.

![추적시스템 구성도1](https://user-images.githubusercontent.com/41908146/91866810-ded1a500-ecad-11ea-9454-9e549c32203b.png)

### < 객체 추적 모델 구성도 >
분석 알고리즘 모델의 경우 위에서 언급했던 CenterNet 알고리즘을 사용한다.
CenterNet 알고리즘을 사용하는 이유는 상대적으로 빠른 속도와 비교적 높은 분류 정확도 그리고 사람의 관절인 Keypoint를 측정하고 추정해주는 자세 추정(Pose Estimation)의 정확도가 비교적 높기 때문이다. 아래 그림은 CenterNet 알고리즘을 활용해서 객체검출과 자세 추정한 결과이다.

## 기대효과

1. 안전성과 신뢰성 확보
2. 검거율 향상
3. 비용 절감
4. 시간 감축
5. 타 분야에 대한 활용도 용이