# MobileNet_TrainingResult
[MobileNet](https://arxiv.org/pdf/1704.04861.pdf) 을 기반으로 다양한 MobileNet모델을 학습한 결과를 저장

논문 요약 : [블로그](https://westofsky.github.io/posts/paper-review-mobilenet/)
<br/>

기본으로 CIFAR10용 MobileNet 코드를 기반으로 작성하였다. 총 Layer은 아래 표 참고
![image](https://github.com/westofsky/MobileNet_TrainingResult/assets/15906101/f0ff264b-1a19-4609-9a82-3696d6b8dbd8)

파일 별로 hyper parameter을 조절하거나 layer을 바꾸는 등은 Underscore(_)로 구분 구분표는 아래 `파일 구분` 참고
## 파일 구분

- `batch{number}` : {number}만큼 batch size 설정
- `adam` : optimizer
- `ep{number}` : {number} 만큼 epoch 설정
- `width{number}` : {number} 만큼 width multiplier 조절
- `decay` : weidth decay를 1e-4로 설정
- `SEblock` : SENet 신경망 추가
- `Relu6` : Activation함수로 Relu가 아닌 Relu6 사용
- `initialize` : He initialization 사용
- `dropout` : dropout 기법 사용( batch32는 대부분 dropout 기법이 defalut로 들어가있음)
- `28x28` : Resolution multiplier값 조절( CIFAR10 크기를 32x32 -> 28x28)
- `layer{number}` : 기본적으로 CIFAR10용 코드에서 제공하는 28개의 layer중 몇 개를 제거하여 {number}개 만큼의 layer로 모델 구성

## Reference
https://github.com/kuangliu/pytorch-cifar/blob/master/models/mobilenet.py <br> 
https://deep-learning-study.tistory.com/561<br>
https://junha1125.github.io/blog/pytorch-docker-git/2020-08-01-CIFAR10_costom/ <br>https://tutorials.pytorch.kr/beginner/blitz/cifar10_tutorial.html#id1<br>
https://pypi.org/project/ptflops/ <br>
