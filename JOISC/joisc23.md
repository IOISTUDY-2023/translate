JOISC 2023 solution

# Conveyor

# Mizuyoukan 2
임의의 해에서 좌우의 값보다 작은 원소(구간)을 작은 묶음, 그렇지 않은 원소를 큰 묶음이라 하자.


관찰 1. 작은 묶음의 길이가 1인 해만 고려해도 충분하다.
작은 묶음의 길이가 2인 해가 있었다 하자. 작은 묶음의 끝의 원소 하나를 인접한 큰 묶음으로 옮겨도 조건을 만족한다.

관찰 2. 최적해에서 큰 묶음의 경우 길이가 $2 \lceil \log_2{L} \rceil$ 이하이다.