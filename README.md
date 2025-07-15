# 17일차

## 어제 말했던 500줄 길이의 CNN 예제 코드 분석
 1. ReLU (Rectified Linear Unit) : 입력이 0 이하면 0으로 출력, 0 이상일 때는 입력값 그대로 출력
 -> 계산이 매우 단순하여 학습 속도가 빠름<br>
2. Softmax : 3개의 정답 라벨에 대응되는 출력값을 총합이 1이되는 확률분포로 볼수있게함.

<img width="236" height="65" alt="image" src="https://github.com/user-attachments/assets/993c84c3-236c-4c8e-b421-da2f2c8f6dc1" /><br>
-> 다중 클래스 분류의 출력층에서 각 클래스에 대한 확률 분포를 만들어 줌
3. Dropout(0.5) : 신경망이 학습할 때 **절반(50%)**의 뉴런을 랜덤하게 꺼서(drop) 과적합(overfitting) 방지
-> 평가,추론 단계에선 모든 뉴런을 써야함. 학습할때만 드롭아웃을 적용하는것.
4. Dense(units, activation='relu') : 해당 레이어가 가지는 뉴런(출력 노드)의 개수, 적용시킬 활성화 함수는 'relu' 선택
-> 정답 클래스 3개에 대한 출력 클래스에 softmax를 적용한 확률분포를 보고 정답 판단<br>
-> 컨볼루션 레이어는 특징맵을 추출하고, Dense 레이어가 그걸 기반으로 분류(classification)하는 역할을 합니다.
