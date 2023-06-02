# Navigation 2(joisc 2021)
# 문제
+ JOI 왕국은 바다로 둘러싸인 섬입니다. JOI Kingdom의 땅은 N개의 행과 N개의 열로 구성된 정사각형 격자의 그리드입니다. 세로 방향은 남북 방향이고 가로 방향은 서동 방향입니다.
북쪽에서 $(r + 1)$번째 행 $(0 ≤ r ≤ N − 1)$과 서쪽에서 $(c + 1)$번째 열 $(0 ≤ c ≤ N − 1)$에 있는 격자를 격자 $( r, c)$라고 부릅니다.      
<br/> JOI 왕국의 여왕 Anna는 Bruno를 파티에 초대합니다. 그녀는 지금 파티 장소를 선택하고 있습니다. 그녀는 $K(=7)$개의 파티가 열릴 가능성이 있는 후보 격자들을 선택했습니다.      
후보 격자는 0부터 $K-1$까지 번호가 매겨진다. i번째 후보격자는 격자 $(R_i, C_i)$이다. 모든 후보 격자는 바다에 인접하지 않았습니다.
파티 장소는 파티 당일 결정됩니다.      
<br/>파티 전날, Anna는 Bruno가 길을 잃지 않고 파티 장소에 도착할 수 있도록 모든 격자에 깃발을 꽂을 것입니다. 각 깃발에 Anna는 1에서 1,000,000,000 사이의 정수를 씁니다.      
파티 당일에는 후보 격자의 인덱스 $t(0 ≤ t ≤ K − 1)$만 Bruno에게 알려줍니다. 그 후 Bruno는 헬리콥터를 타고 바다와 인접하지 않은 격자에 도착합니다. 그런 다음 Bruno는 파티 장소로 이동하기 시작합니다.
Bruno는 자신이 어디에 있는지 모르지만 동서남북 방향은 알고 있습니다. Bruno는 현재 셀과 주변 8개 격자에서만 깃발을 볼 수 있습니다.       
<br/> 즉, Bruno가 격자 $(a, b)(1 ≤ a ≤ N − 2, 1 ≤ b ≤ N − 2)$에 있을 때 다음 9개 격자의 플래그만 볼 수 있습니다.      
 $(a - 1, b - 1), (a - 1, b), (a - 1, b + 1), (a, b - 1), (a, b), (a, b + 1), (a + 1, b - 1), (a + 1, b), (a + 1, b + 1)$      
<br/> 브루노는 다음 5가지 행동 중 하나를 취할 수 있습니다.      
+ 행동 0: Bruno는 동쪽으로 한 칸 이동합니다. 즉, 격자 $(a, b)$에서 격자 $(a, b + 1)$로 이동합니다.   
+ 행동 1: Bruno는 서쪽으로 한 칸 이동합니다. 즉, 격자 $(a, b)$에서 격자 $(a, b − 1)$로 이동합니다.   
+ 행동 2: Bruno는 남쪽으로 한 칸 이동합니다. 즉, 격자 $(a, b)$에서 격자 $(a + 1, b)$로 이동합니다.   
+ 행동 3: Bruno는 북쪽으로 한 칸 이동합니다. 즉, 격자 $(a, b)$에서 격자 $(a − 1, b)$로 이동합니다.   
+ 행동 4: Bruno는 파티가 현재 자신의 격자에서 열릴 것이라고 생각하고 거기에 머뭅니다. 즉, 그는 움직이지 않습니다.   
<br/> 파티에 늦게 도착해선 안되기 때문에 Bruno는 가능한 한 행동의 수를 최소화하면서 파티 장소로 이동해야 합니다. 따라서, 이런 조건하에 Bruno는 바다에
인접한 격자에 절대 들어가지 않습니다.   
<br/> 깃발에 큰 정수를 쓰는 것은 번거롭기 때문에 Anna는 깃발에 쓰는 최대 정수를 최소화하려고 합니다.
<br/> Anna의 전략과 Bruno의 전략을 구현하는 프로그램을 작성하십시오. Anna는 깃발에 정수를 적고 Bruno는 최소한의 행동으로 파티 장소에 도착해야합니다.
# 구현
총 2개의 파일을 구현해야 합니다.   
<br/> 첫 번째 파일은 Anna.cpp입니다. Anna의 전략을 구현해야 합니다. 다음 기능을 구현해야 합니다. 프로그램은 전처리 지시문 #include를 사용하여 Anna.h를 포함해야 합니다.   
<br/>
+ void Anna(int N, int K, std::vector<int> R, std::vector<int> C)   
+ 이 함수는 깃발에 정수를 쓰는 Anna의 전략을 구현합니다. 각 시나리오(스코어링 참조)에 대해 이 함수는 처음에 정확히 한 번 호출됩니다.   
+ 파라미터 N은 JOI 왕국의 땅이 N 행과 N 열로 구성된 정사각형 격자의 그리드임을 의미합니다.   
+ 파라미터 K는 파티의 후보 격자의 개수 $K(=7)$입니다.   
+ 파라미터 R과 C는 길이 K의 배열입니다. 여기서 R[i]와 C[i] $(0 ≤ i ≤ K − 1)$는 후보 셀 i의 셀 $(Ri, Ci)$을 나타냅니다.   
+ 파라미터 N, K, R[i] 및 C[i](0 ≤ i ≤ K − 1) 값의 범위는 제약 조건을 참조하십시오.   
+ Anna에 대한 각 함수 호출에 대해 다음 함수는 정확히 $N^2$번 호출되어야 합니다. 모든 격자에 대해 한 번씩 호출해야 합니다.   
<br/>
+ void SetFlag(int r, int c, int 값)
매개변수 r 및 c는 Anna가 셀(r, c)의 플래그에 정수를 쓴다는 것을 의미합니다. 여기서 0 ≤ r ≤ N-1, 0 ≤ c ≤ N-1을 만족해야 한다. 이 조건이 만족되지 않으면 프로그램이 오답[1]으로 판정됩니다.
매개변수 값은 Anna가 플래그에 쓰는 정수입니다. 여기서 1 ≤ value ≤ 1 000 000 000을 만족해야 합니다. 이 조건이 만족되지 않으면 프로그램이 오답[2]으로 판정됩니다.
함수 SetFlag가 동일한 매개변수(r, c)로 두 번 이상 호출되면 프로그램이 오답으로 판단됩니다[3].
Anna 함수가 종료될 때 SetFlag 함수에 대한 함수 호출 횟수가 N2와 다르면 프로그램이 오답[4]으로 판단됩니다.
SetFlag 함수에 대한 함수 호출이 오답으로 간주되면 프로그램이 즉시 종료됩니다.