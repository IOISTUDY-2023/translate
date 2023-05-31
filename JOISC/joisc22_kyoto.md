# Fences

## 문제

교토시는 세계적인 관광명소다. 또한, 격자 모양의 도로들의 도시로도 알려져 있다. 당신은 교토로 여행을 왔다. 그리고 당신은 어떤 유명한 장소를 걸어서 가기로 했으며, 가능한 짧은 시간 안에 도착하고 싶다. 이 문제에서는, 다음과 같은 단순화된 상황을 가정한다.

이 도시에서는, 동서 방향으로 $H$개, 그리고 남북 방향으로 $W$개의 도로가 있다. 즉, 도시는 $(H-1) \times (W-1)$개의 칸으로 이루어진 격자 모양이다. 이때 북쪽에서 $i$번째 도로와($1 \leq i \leq H$) 서쪽에서 $j$번째 도로의($1 \leq j \leq H$) 교차점을 $(i,j)$라고 표현한다.

다른 도로들은 다른 너비, 재질, 그리고 밀집도를 가지고 있을 수가 있다. 그러므로 당신의 걷는 속도는 도로마다 다를수가 있다. 각 도로에 대해서, 당신의 걷는 속도는 다은과 같이 결정된다.

* 만약 당신이 북쪽에서 $i$번째 도로($1 \leq i \leq H$)에서 걸으면, $A_i$초가 걸린다. 다른 말로, 모든 $c(1 \leq c \leq W-1)$에 대해, ($i,c$)에서 ($i,c+1$)로 이동하는데 $A_i$초가 걸린다.
* 만약 당신이 북쪽에서 $j$번째 도로($1 \leq j \leq H$)에서 걸으면, $B_j$초가 걸린다. 다른 말로, 모든 $r(1 \leq r \leq H-1)$에 대해, ($r,j$)에서 ($r+1,j$)로 이동하는데 $B_i$초가 걸린다.

교토시의 아름다운 지형을 파괴하면 안돼기에, 도로 밖에서 걸을 수는 없다.

현재 당신은 $(1,1)$을 건너고 있다. 당신은 $(H,W)$에 있는 교차로로 가고 싶다. 만약 길게 걸으면 피곤하니까, 딴 길로 세면 안된다. 즉, 북쪽, 혹은 서쪽으로는 이동하지 않는다. 이 조건 만족하에, 당신은 최대한 빨리 도착하고 싶다.

도로에 대한 정보가 주어질 때, $(1,1)$에서 $(H,W)$까지 가는 최단경로를 계산하는 프로그램을 만들어라.

## 입력

아래의 정보가 입력으로 주어진다. 모든 값은 정수다.

$H W$

$A_1 A_2 \cdots A_H$

$B_1 B_2 \cdots B_W$

## 출력

표준 출력으로 한 줄을 출력한다. 출력값은 $(1,1)$에서 $(H,W)$까지 다른 길로 세지 않고 가는 최소 시간(초)이 있어야 한다.

## 제한

* $2 \leq H \leq 100000$.
* $2 \leq W \leq 100000$.
* $1 \leq A_i \leq 1000000000(=10^9)$ $(1 \leq i \leq H)$.
* $1 \leq B_j \leq 1000000000(=10^9)$ $(1 \leq j \leq W)$.

## 서브태스크

|번호|배점|제한|
|---|---|---|
|1|10|$H \leq 1000, W \leq 1000$.|
|2|30|$A_i \leq 1000(1 \leq i \leq H)$, $B_j \leq 1000(1 \leq j \leq W)$.|
|3|60|추가적인 제한이 없다.|

## 예제 입출력 1

### 예제 입력 1

2 2
1 3
2 5

### 예제 출력 1

5

$(1,1)$에서 $(2,2)$로 이동할 수 있는 경로는 총 2가지가 있다.

* 다음과 같은 방법으로 이동한다: $(1,1) \rightarrow (1,2) \rightarrow (2,2)$. 총 $A_1 + B_2 = 1 + 5 = 6$ 초가 걸린다.
* 다음과 같은 방법으로 이동한다: $(1,1) \rightarrow (2,1) \rightarrow (2,2)$. 총 $B_1 + A_2 = 2 + 3 = 5$ 초가 걸린다.

최소시간이 5초이므로, 5를 출력한다. 이 두가지 방법은 아래에 그림에 나타나 있다. 그림에 있는 숫자는 그에 해당하는 도로에 걷는데 걸리는 시간이다.

![sample](https://cdn.discordapp.com/attachments/939736755471532032/1110853635262394368/image.png)

이 입력은 모든 서브태스크들의 조건을 만족시킨다.

## 예제 입출력 2

### 예제 입력 2

5 5
7 1 5 2 8
7 2 4 1 6

### 예제 출력 2

20

예를 들어 아래와 같은 방법으로 이동하면 20초가 걸린다. 19초로 이동하는 것은 불가능하므로, 20을 출력한다. 그림에 있는 숫자는 그에 해당하는 도로에 걷는데 걸리는 시간이다.

![sample2](https://cdn.discordapp.com/attachments/939736755471532032/1110854124616036382/image.png)

이 입력은 모든 서브태스크들의 조건을 만족시킨다.

## 예제 입출력 3

### 예제 입력 3

4 6
454863204 543362989 866044086 813602010
71574269 17945210 688720933 392135202 38174709 168241720

### 예제 출력 3

2737473954

이 입력은 서브태스크 1,3의 조건을 만족시킨다.