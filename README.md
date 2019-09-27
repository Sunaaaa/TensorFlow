# TensorFlow
빅데이터 저장 및 분석 시스템 구축 기술 

# CNN : Convolutional Neural Networks

- 주어진 이미지에 필터를 이용하여, 특정 특징을 갖는 여러 형태의 작은 이미지로 학습을 진행한다.
- 하나의 이미지에서 특징만 뽑아낸 다수의 이미지로 학습하여 제대로 된 학습을 수행한다.



- CNN에서의 학습의 대상은 필터 파라미터 
  - Convolution : 합성곱
    - 지정한 개수의 지정한 크기의 필터로 합성곱 연산을 수행한다.
    - 합성곱 처리 결과, Feature Map을 만든다.
  - Convolution Layer : 특정 특징을 갖는 여러 형태의 작은 이미지
    - Convolution 연산을 활용해서 Input Image의 특징을 찾는 과정을 수행한다.
  - Filter : Image의 특징(feature)을 찾아내기 위한 공용 파라미터 , CNN에서는 Kernel 이라고도 한다. 
    - 일반적으로 정사각 행렬로 정의된다.
    - Input Image의 모든 영역을 훑으면서 특정 특징(feature)을 뽑는다.
      - Input Image를 지정한 간격으로 순회하면서 합성곱을 계산한다.
  - Stride : 필터가 Input Image를 순회하하고 합성곱을 계산하는 간격
    - 필터가 움직이는 간격
    - 1 pixel == 1 Stride 
  - Padding : Convolution Layer의 출력 데이터가 줄어드는 것을 방지하는 방법
    - Filter와 stride의 작용으로 Feature Map의 크기는 Input Image보다 작아진다. 이 때, padding을설정하여 데이터의 크기가 줄어드는 것을 방지할 수 있다. 
    - 입력 데이터의 외각에 지정된 픽셀만큼 특정값으로 채워 넣는다. 
    - 일반적으로 0으로 채운다.
  - Activation Map : Input Image에 대해서 Filter를 통해 뽑은 Feature을 그린 
  - Image 
    - (31,31,3) : 높이와 폭이 31 픽셀인 컬러 사진 데이터
    - (31,31,1) : 높이와 폭이 31 픽셀인 흑백 사진 데이터
- 랜덤으로 필터 값을 적용하여 사이즈를 줄이고, 특징을 뽑아서) 하나의 그림을 여러개의 특징을 가진 작은 이미지(Convolution Layer)로 학습 
  - 같은 형태지만 조금씩 다른 모양의 입력값이 주어진다.
  - Convolution 작업을 통해 여러 형태의 그림으로 쫙 펼친 뒤, 학습
- 단, 너무 많은 Convolution 은 특징이 흐려지기 때문에 학습의 의미가 없어지기 때문에 적정한 Convolution을 진행해야한다. 
- 해당 그림의 특징을 가진 여러 개로 학습
- Convolution Layer의 값이 커지는 것을 방지하여 ReLu 를 수행
- 여러개의 필터를 사용하여 여러 개의 Convolution Layer(Activation maps)를 생성 
- convolution을 거쳐 나온 데이터를 Neural Network의 입력데이터(palceholder)로 사용한다.
