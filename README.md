# characteristics of each stage.Rmd
BMR, King, MiToS stage각각에 대해서 단계별로 대응되는 ALSFRS-R 확인
BMR, MiToS는 평균치가 서서히 감소하는 경향을 보여주나 King은 확연한 감소치는 안보임. 


# stages of patients at the time of diagnosed and enrolled.Rmd
첫방문시점의 stage분포 비교
BMR은 stage 1이 10546명으로 가장 많고 2,3,4,5순으로 감소하는 분포를 보이며 골고루 보임. 
King's stage는 stage 2가 가장 많고 1,3,4도 비슷비슷한 정도로 많음.
MiToS stage는 stage 0이 압도적으로 많은 23354명이며 stage 1이 4980명, stage 2이상은 거의 없는 분포를 보임. 


# estimate the slope of ALSFRS-R total score within each stage.Rmd
BMR stage는 stage가 증가함에 따라서 시작시점의 ALSFRS가 감소하고 감소기울기도 조금씩 증가하는 모습을 보이나 stage 3,4,5,6의 기울기에 확연한 차이는 보이지 않음.
King stage는 기울기 감소가 확연하게 잘 보이여 MiToS는 기울기 감소가 뚜렷하지 않음.


# Changes of stages with disease progression.Rmd
시간이 지남에 따라서 stage가 증가하는 모습을 확인
BMR stage는 시간이 지남에 따라서 대체로 stage가 증가하고 세 stage중에서 가장 밀집되어 증가하는 분포를 보임.


# distribution of ALS stage last recorded in 12 month period by baseline stage.Rmd
첫방문과 9~15개월즈음 f/u데이터가 있는 대상자들의 f/u stage변화 분포확인
세 stage중에서 첫방문시점의 stage가 가장 폭넓게 분포하고 진행양상이 stage가 다양하게 나타나서 환자들마다 진행하는 속도가 다른것을 잘 보여줌.


# standardised time from symptom onset to each stage.Rmd
standardized time분포의 균일한 정도를 비교해보면
BMR stage는 stage 1,2,3사이와 4,5사이는 비슷한 간격으로 분포하나 3,4사이와 5,6사이는 균일하지 않음.
King's stage는 각 stage사이의 간격이 모두 제각각임.
MiToS는 0,1,2는 비슷하나 후기에 치우치고 간격이 매우 작음. 세 stage중에서는 BMR이 비교적 가장 균일하게 진행양상을 보여주는것으로 보여짐.


# stage transition probabilities (based on Markov model)
stage별로 다음 방문시점의 stage transition probability비교
각 subject별로 방문시점이 다르고 간격도 매우 heterogenous하므로 
이부분에 대한 해결을 하고 난뒤 재분석이 필요함.

## To do list
- stage 0 를 어떻게 처리할 것인지? 
stage 0 라면 이론적으로는 asymptomatic stage 를 말하는데, stage estimation 과정에서 alsfrs item 중 Q2 and Q9가 제외되면서 해당 결과가 발생
- onset_delta 는 day 단위인데 30으로 나눠서 month로 전환했으므로 day를 365로 나누고 12를 곱해주는 방법으로 재계산 필요
- standardized time 
사망한상태인 경우 사망시점은 무조건 standardised time이 1이어야 하나 1미만의 수치를 보이는 케이스는 제외했는데 4 case가 이런 경우에 해당함. 왜 이런지?
- stage transition probability
관측 시점이 환자들간에, 그리고 환자 내에서도 동일하지 않고, uneven 하기 때문에, 단순 계산은 적절치 않으므로 해결방법이 필요함
