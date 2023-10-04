# Airline Route Map(joisc 2018)
# 문제
앨리스는 JOI 왕국에 살고 있습니다. 그녀는 IOI공화국에 살고 있는 밥을 초대할 것입니다.   
그녀는 그를 초대하기 전에 JOI 왕국의 항공 노선도를 그에게 보낼 계획입니다.   
JOI 왕국은 0부터 $N-1$까지 N개의 섬으로 이루어진 섬나라입니다.   
JOI 왕국에는 M개의 항공 노선이 있습니다. 각 i(0 ≤ i ≤ M−1)에 대해 (i + 1)번째 항공 노선은 $A_i$
섬과 $B_i$ 섬을 양방향으로 연결합니다. 동일한 두 섬을 연결하는 두 항공노선은 없습니다.   
그녀는 JOI 왕국이 운영하는 특수 전신기를 사용해야 합니다. 그녀는 전신기를 사용하여 방향이
없는 그래프를 보낼 수 있습니다. 그러나 이를 사용하면 각 섬과 항공노선의 번호는 무작위로
섞이게 됩니다.   
   
정확하게는 아래와 같이 정보가 전송됩니다. G를 앨리스가 보낸 그래프라고 합시다.    
(V를 G의 정점 수, U를 G의 간선 수라고 가정합니다.)   
   
앨리스는 G의 정점 수 V와 G의 간선 수 U를 지정합니다. 그런 다음 각 숫자 0, 1,
. . . , V − 1 을 각 정점에, 숫자는 각각 0, 1, . . . , U − 1 각 간선에 부여합니다.   
Alice는 매개변수 $C_0, C_1, . . . , C_{U−1}$ 및 $D_0, D_1, . . . , D_{U-1}$를 결정합니다.    
이러한 매개변수는
G의 간선을 나타냅니다. 즉, 각 $j(0 ≤ j ≤ U − 1)$에 대해 G의 j번째 간선은 정점 {C_j}와 정점
{D_j}를 연결합니다.    
G의 정점들의 번호는 JOI Kingdom에 의해 섞입니다. 먼저 JOI Kingdom은 0,1,...V-1의 순열인 
p[0], p[1], . . . , p[V − 1],을 생성합니다. 이후 $C_0, C_1, . . . ,C_{U−1}$은 $p[C_0], p[C1],
. . . , p[C_{U-1}]$ 로 대체되며, $D_0, D_1, . . . , D_{U−1}$은 $p[D_0], p[D_1], . . . , 
p[D_{U-1}]$로 대체됩니다.   
그런 다음 JOI Kingdom에서 G의 간선들의 번호를 섞습니다. 먼저 JOI Kingdom은 0,1,...,U-1의 순열인
q[0], q[1], . . . , q[U − 1]을 생성합니다. 이후 
$C_0, C_1, . . . ,C_{U−1}$은 $C_{q[0]},C_{q[1]}, . . . ,C_{q[U−1]}$로 대체되며, 
$D_0, D_1, . . . , D_{U−1}$은 
$D_{q[0]}, D_{q[1]}, . . . , D_{q[U-1]}$으로 대체됩니다.
다음 데이터가 Bob에게 전송됩니다: V 및 U 값, 매개변수 $C_0, C_1, …C_{U-1}, D_0,D_1,...,D_{U-1}$의
새로운 값   
   
이 전신기를 사용하면 단순 그래프만 보낼 수 있습니다. 여기서 단순 그래프란 다중 간선과 
자가 루프가 없는 그래프를 의미합니다.   
   
즉, 다음 조건을 만족하는 그래프를 보낼 수 있습니다: $(C_i, D_i) , (C_j, D_j)$ 및 $(C_i, D_i) , 
(D_j, C_j)$는
모든 i, j에 대해 만족됩니다$(0 ≤ i < j ≤ U − 1), C_i, D_i$는 모든 $i(0 ≤ i ≤ U − 1)$에 대해
만족됩니다.   
   
Alice는 최대한 적은 정점을 가진 그래프를 사용하여 JOI Kingdom의 항공사 노선도를 Bob에게 보내고
싶어합니다.   
   
Alice와 Bob 사이의 통신을 돕기 위해 다음 두 프로그램을 작성하십시오.   
   
JOI 왕국의 섬 수 N, JOI 왕국의 항공 노선 수 M, JOI 왕국의 항공사 노선도를 나타내는
수열 A, B가 주어지면 첫 번째 프로그램은 앨리스가 보낸 그래프 G의 정보를 출력합니다.   
Bob이 수신한 그래프 G의 정보를 바탕으로 두 번째 프로그램은 JOI Kingdom의 항공 노선 지도를
복구합니다.   
# 구현
두 개의 파일을 제출해야 합니다.   
    
첫 번째 파일은 Alice.cpp입니다. 이 파일은 Alice가 보낸 그래프의 정보를 출력합니다.   
다음 기능을 구현해야 합니다. 프로그램에는 Alicelib.h가 포함되어야 합니다.   
   
void Alice( int N, int M, int A[], int B[] )   
각 테스트케이스에 대해 이 함수는 한 번 호출됩니다.   
매개변수 N은 JOI 왕국의 섬 수입니다.   
매개변수 M은 JOI 왕국의 항공사 노선 수입니다.   
매개변수 A[], B[]는 JOI 왕국의 항공 노선도를 설명하는 길이 M의 수열입니다.   
함수 Alice는 다음 함수를 사용하여 Alice가 보낸 그래프 G의 정보를 출력합니다.   
   
void InitG(int V, int U)   
이 함수는 G의 정점 수와 G의 간선 수를 결정합니다.   
매개변수 V는 G의 정점 수입니다. 매개변수 V는 1에서 1500 사이의 정수여야 합니다. 이 함수에 대한
호출에 이 범위를 벗어난 매개변수가 있는 경우 프로그램은 틀렸습니다[1]으로 간주됩니다.   
매개변수 U는 G의 간선 수입니다. 매개변수 U는 0과 $V(V − 1)/2$ 사이의 정수여야 합니다.   
이 함수에 대한 호출에 이 범위를 벗어나는 매개변수가 있는 경우 프로그램은 틀렸습니다[2]으로
간주됩니다.   
   
void MakeG( int pos, int C, int D )   
이 함수는 G의 간선을 결정합니다.   
매개변수 pos는 호출에 의해 지정된 간선의 번호입니다. 매개변수 pos는 0과 U − 1 사이의
정수여야 합니다. 이 함수에 대한 호출에 이 범위를 벗어난 매개변수가 있는 경우 프로그램은
틀렸습니다[3]으로 간주됩니다. 이 함수는 동일한 매개변수 pos를 사용하여 두 번 이상 호출하면
안 됩니다. 이 함수가 동일한 매개변수로 두 번 이상 호출되면 프로그램은 틀렸습니다[4]으로 간주됩니다.   
매개변수 C와 D는 그래프 G의 간선에 포함된 두 정점입니다. C와 D는 0과 V − 1 사이의 
정수여야 합니다. 또한 C ≠ D를 만족해야 합니다. C나 D가 이러한 조건을 만족하지 않으면
귀하의 프로그램은 틀렸습니다[5]으로 간주됩니다.   
여기서 U와 V는 InitG에서 지정한 정수이다.   
    
Alice 함수에서는 InitG 함수를 한 번 호출한 후 MakeG 함수를 정확히 U번 호출해야 합니다.    
InitG 함수가 두 번 호출되면 프로그램은 잘못된 틀렸습니다[6]으로 간주됩니다. InitG 함수가
호출되기 전에 MakeG 함수가 호출되면 프로그램은 틀렸습니다[7]으로 간주됩니다. Alice 함수가
종료될 때 InitG가 호출되지 않거나 MakeG 함수가 U번 호출되지 않으면 프로그램은 틀렸습니다[8]으로
간주됩니다. Alice 함수가 종료되었을 때, Alice가 설명한 그래프 G가 단순 그래프가 아닌 경우, 
귀하의 프로그램은 틀렸습니다[9]으로 간주됩니다.   
   
Alice 함수에 대한 호출이 잘못된 답변으로 간주되면 프로그램이 즉시 종료됩니다.   
   
두 번째 파일은 Bob.cpp입니다. 이 파일은 Bob이 수신한 그래프 G의 정보를 바탕으로 JOI Kingdom의
항공 노선도를 출력합니다. 다음 기능을 구현해야 합니다. 프로그램에는 Boblib.h가 포함되어야 합니다.   
   
void Bob( int V, int U, int C[], int D[] )   
각 테스트 사례에 대해 이 함수는 한 번 호출됩니다.   
매개변수 V는 그래프 G의 정점 수입니다.   
매개변수 U는 그래프 G의 간선 수입니다.   
매개변수 C[], D[]는 그래프 G의 간선을 나타내는 길이 U의 수열입니다.   
Bob 함수는 다음 함수를 이용하여 JOI Kingdom의 항공사 노선도를 복구하고, 항공사 노선도
정보를 출력해야 합니다.   
   
void InitMap(int N, int M)
이 함수는 JOI 왕국의 섬 수와 JOI 왕국의 항공 노선 수를 지정합니다.   
매개변수 N은 JOI 왕국에서 복구된 섬의 개수입니다. N은 JOI 왕국의 실제 섬 수와 동일한 정수여야 합니다.
동일하지 않으면 프로그램은 틀렸습니다[10]으로 간주됩니다.   
매개변수 M은 JOI 왕국에서 복구된 항공노선 수이다. M은 JOI 왕국의 실제 항공노선의 수와 동일한
정수여야 합니다. 동일하지 않으면 프로그램은 틀렸습니다[11]으로 간주됩니다.  

void MakeMap(int A, int B)   
이 함수는 JOI 왕국의 항공사 노선 수를 지정합니다.   
매개변수 A와 B는 섬 A와 섬 B를 연결하는 항공 노선이 있음을 의미합니다. A와 B는 0과 N − 1 사이
의 정수입니다. 또한 A ≠ B를 만족해야 합니다. A 또는 B가 이러한 조건을 만족하지 않으면 
귀하의 프로그램은 틀렸습니다[12]으로 간주됩니다. JOI Kingdom에 A섬과 B섬을 연결하는 항공노선이
없다면 귀하의 프로그램은 틀렸습니다[13]으로 간주됩니다. 이 함수 호출로 설명되는 항공 경로는
이전 호출의 항공 경로와 달라야 합니다. MakeMap( A, B )가 호출될 때 MakeMap( A, B ) 또는 
MakeMap( B, A )가 이미 호출된 경우 프로그램은 틀렸습니다[14]으로 간주됩니다.   
여기서 N은 InitMap이 지정한 정수값입니다.   
   
Bob 함수에서는 InitMap 함수를 한 번 호출한 후 MakeMap 함수를 정확히 M번 호출해야 합니다. 
InitMap 함수가 두 번 호출되면 프로그램은 틀렸습니다[15]으로 간주됩니다. InitMap 함수가 
호출되기 전에 MakeMap 함수가 호출되면 프로그램은 틀렸습니다[16]으로 간주됩니다.    
Bob 함수가 종료될 때 InitMap이 호출되지 않거나 MakeMap 함수가 M번 호출되지 않으면
프로그램은 틀렸습니다[17]으로 간주됩니다. 여기서 M은 InitMap에서 지정한 정수 값입니다.   
   
Bob 함수에 대한 호출이 잘못된 응답으로 간주되면 프로그램이 즉시 종료됩니다.   
   
# 입력
샘플 그레이더는 표준 입력에서 다음 데이터를 읽습니다.   
   
첫 번째 줄에는 공백으로 구분된 두 개의 정수가 포함되어 있습니다. 이는 JOI 왕국이 N개의 섬으로 
구성되어 있고 JOI 왕국에 M개의 항공 노선이 있음을 의미합니다.   
다음 M개의 줄에는 항공사 노선에 대한 정보가 포함되어 있습니다. (i + 1)번째 
줄(0 ≤ i ≤ M − 1)에는 공백으로 구분된 두 개의 정수 $A_i, B_i$가 포함되는데, 이는 i번 항공노선이
잇는 두 섬의 번호를 나타냅니다.     
# 출력
프로그램이 성공적으로 종료되면 샘플 그레이더는 다음 정보를 표준 출력에 씁니다. 
(실제 따옴표는 쓰지 않습니다.)   
   
+ 프로그램이 오답으로 간주되면 샘플 그레이더는 해당 유형을 “틀렸습니다[1]” 형식으로 작성하고 
종료합니다.   
+ Alice와 Bob에 대한 호출 중 하나라도 잘못된 답변으로 간주되지 않으면 샘플 그레이더는 
"Accepted"라고 씁니다. 또한 V의 값을 출력합니다.   
+ 귀하의 프로그램이 여러 유형의 오답으로 간주되는 경우 샘플 그레이더는 그 중 하나만 보고합니다.
# 제한
$1 ≤ N ≤ 1 000$.   
$0 ≤ M ≤ N(N − 1)/2$.   
$0 ≤ A_i ≤ N − 1 (0 ≤ i ≤ M − 1)$.   
$0 ≤ B_i ≤ N − 1 (0 ≤ i ≤ M − 1)$.   
$A_i ≠ B_i (0 ≤ i ≤ M − 1)$.   
$(A_i, B_i) ≠ (A_j, B_j) and (A_i, B_i) ≠ (B_j, A_j) (0 ≤ i < j ≤ M − 1)$.   
# 점수
서브태스크 1 또는 서브태스크 2에서 프로그램이 모든 테스트케이스를 해결하면 만점을 얻습니다.   
서브태스크 3에서 프로그램이 모든 테스트케이스를 해결하면 점수는 다음과 같이 계산됩니다. MaxDiff를
V − N의 최대값으로 설정합니다.   
101 ≤ MaxDiff일 때 점수는 0입니다.   
21 ≤ MaxDiff ≤ 100일 때 점수는 $13 + [(100 − MaxDiff)/4]$입니다. 여기서 [x]는 x를 초과하지 않는
가장 큰 정수입니다.   
13 ≤ MaxDiff ≤ 20일 때 점수는 $33 + (20 − MaxDiff) × 3$입니다.   
MaxDiff가 12 이하이면 점수는 63입니다.   
## 예제
다음은 샘플 그레이더에 대한 샘플 입력과 그에 대응되는 함수의 호출입니다.   
<table>
  <tr>
    <td rowspan="2">예시 입력1</td>
    <td colspan="4">예시 호출</td>
  </tr>
  <tr>
    <td>호출</td>
    <td>반환</td>
    <td>호출</td>
    <td>반환</td>
  </tr>
  <tr>
    <td rowspan="20">4 3<br/>0 1<br/>0 2<br/>0 3<br/></td>
    <td> Alice(...)</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
  <td></td>
  <td>InitG(4,3)</td>
  <td></td>
  </tr>
  <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
  <tr>
    <td></td>
  <td></td>
  <td>MakeG(0,0,1)</td>
  <td></td>
  </tr>
  <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
  <tr>
    <td></td>
  <td></td>
  <td>MakeG(1,0,2)</td>
  <td></td>
  </tr>
   <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
    <tr>
    <td></td>
  <td></td>
  <td>MakeG(2,0,3)</td>
  <td></td>
  </tr>
     <tr>
    <td></td>
  <td>(none)</td>
  <td></td>
  <td></td>
  </tr>
      <tr>
    <td>Bob(...)</td>
  <td></td>
  <td></td>
  <td></td>
  </tr>
      <tr>
    <td></td>
  <td></td>
  <td>InitMap(4,3)</td>
  <td></td>
  </tr>
    <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
    <tr>
    <td></td>
  <td></td>
  <td>MakeMap(0,1)</td>
  <td></td>
  </tr>
    <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
     <tr>
    <td></td>
  <td></td>
  <td>MakeMap(0,2)</td>
  <td></td>
  </tr>
     <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
      <tr>
    <td></td>
  <td></td>
  <td>MakeMap(0,3)</td>
  <td></td>
  </tr>
     <tr>
    <td></td>
  <td></td>
  <td></td>
  <td>(none)</td>
  </tr>
      <tr>
    <td></td>
  <td>(none)</td>
  <td></td>
  <td></td>
  </tr>
</table>

이 경우 Alice(...), Bob(...) 함수에 입력되는 매개변수는 다음과 같습니다.   
<table>
   <tr>
      <td>파라미터</td>
      <td>Alice(...)</td>
      <td>Bob(...)</td>
   </tr>
   <tr>
      <td>N</td>
      <td>4</td>
      <td></td>
   </tr>
   <tr>
      <td>M</td>
      <td>3</td>
      <td></td>
   </tr>
   <tr>
      <td>V</td>
      <td></td>
      <td>4</td>
   </tr>
   <tr>
      <td>U</td>
      <td></td>
      <td>3</td>
   </tr>
   <tr>
      <td>A</td>
      <td>{0,0,0}</td>
      <td></td>
   </tr>
   <tr>
      <td>B</td>
      <td>{1,2,3}</td>
      <td></td>
   </tr>
   <tr>
      <td>C</td>
      <td></td>
      <td>{2,2,2}</td>
   </tr>
   <tr>
      <td>D</td>
      <td></td>
      <td>{3,0,1}</td>
   </tr>
</table>

# 서브태스크
|번호|배점|제한|
|---|---|---|
|1|22|$N \le 10$|
|2|15|$N \le 40$|
|3|63|추가 제약조건이 없습니다.|
+ ## Subtask 1,2. ( $37점$)
 다양한 풀이가 있을 수 있습니다. 추후 풀이로 확장하기 가장 쉬운 풀이는, 그래프의 정점들을 특정한 방식으로 구분하는 풀이입니다. 정점들은 많아야 40개이고 하나의 정점과 연결된 기존의 간선들도 많아야 39개이기 때문에, 예를 들어 1000개의 새로운 정점을 추가한 뒤, 1번 정점을 50개의 새로운 정점과 연결하고, 2번 정점을 100개의 새로운 정점과 연결하고, ..., 10번 정점을 500개의 새로운 정점과 연결하는 방식을 쓰고, 각 새로운 정점들은 서로 연결했다고 해봅시다. 그렇다면 정점의 번호가 사라져도 새로 추가된 정점을 구분할 수 있고, 새로 추가된 간선에 의한 차수를 계산하면 각 정점들이 기존에는 몇번 정점이었는지 알아낼 수 있습니다.
+ ## Subtask 3. ( $100점$)
 위의 풀이에서는 기존의 정점들을 분간해내기 위해 i번 정점에 $k *i$개의 정점을 새로 연결해주었지만, 사실 굳이 선형적인 방식으로 정점을 연결해줄 필요는 없습니다. 왜냐하면 새로운 정점들과 간선들을 적당히 추가하면, 새로운 정점들끼리 구분되도록 할 수 있기 때문입니다. 그렇다면, 어떤 방법을 써야 새로운 정점들을 알아내면서, 그들에게 매겼던 번호도 알아낼 수 있을까요?
 한 가지 생각해볼 수 있는 것은, 이를테면 다음과 같은 방법입니다:
 1. 정확히 하나의 정점을 제외하고 모든 다른 정점들과 연결된 정점(A)과, 연결되지 않은 정점(B) 두 개를 집어넣습니다(이후에 추가하는 정점들과도 연결되어있습니다)
 2. B와 기존에 존재했던 어떤 정점 사이에도 연결은 존재하지 않습니다.
 3. 새로운 10개의 정점들을 추가하는데, 이들끼리는 특정한 트리의 구조로 연결되어있습니다. 또한, B와 이 10개의 정점들을 전부 연결해줍니다.
 4. 새로 추가한 10개의 정점들중 i번째 정점에 대해서, 기존 정점의 i번째 비트가 켜져있다면 해당 정점과 연결합니다.

 이제 이러한 세팅하에서 어떤 방식으로 문제가 풀릴지 생각해봅시다.   
 일단, 첫번째로 지정한 정점인 A는 무조건 찾아낼 수 있습니다. A의 차수는 (전체 정점의 개수-2)입니다. 3번째 스텝에서 추가한 정점들은 트리와 같이 연결되어있기 때문에, 적어도 3개의 정점들에 대해서는 간선이 없습니다. 따라서 용의선상에서 제외됩니다. 2번 스텝에서 추가한 정점의 경우에는, (기존 정점의 개수+1(A)+1(자신))만큼의 정점들과 연결되지 않는데, 따라서 차수가 (전체 정점의 개수-3) 이하입니다. 따라서 B도 아닙니다. 기존에 존재했던 정점들의 경우에는 i번 정점의 경우 (전체 정점의 개수-(10-(i의 켜진 비트수))-2) 이하의 차수를 가지게 되는데, 10개의 비트가 켜진 i는 존재하지 않기 때문에 이들도 조건을 만족할 수 없습니다. 따라서 오로지 A만이 최대 차수를 가집니다.   
 A를 구분했기 때문에, 이제 B도 알아낼 수 있습니다. B를 알아내었다는 것은, B와 연결된 10개의 정점들을 알아낼 수 있음을 의미합니다. 만약 10개의 정점들을 연결한 트리의 상태가 굉장히 비대칭적이라면, 각 정점들이 몇번이었는지 또한 알아낼 수 있을 것입니다(알아내었다고 가정해봅시다.). 그렇다면, 총 10개의 정점이 있으므로 기존의 정점들을 1023번째까지를 표현할 수 있고, 이는 전체 문제의 제한인 1000을 넘으므로 문제가 해결됩니다!   
 비대칭 트리를 구성하는 방법은 몇가지가 있을 수 있는데, 한 가지 방법은 다음과 같습니다:   
(1,2)   
(2,3)   
(3,4)   
(4,5)   
(5,6)   
(6,7)   
(1,8)   
(1,9)   
(9,10)  
실제로 해당 간선들을 통해 트리를 그려보면, 1만이 3의 차수를 가지고 그로부터 파생되는 각 가지들의 길이가 서로 다름을 알 수 있습니다. 따라서 각 가지를 특정할 수 있고, 그 가지에 들어있는 정점들도 구분할 수 있습니다.