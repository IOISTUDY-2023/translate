# JOI 2019 4번 断層 (Geologic Fault)
## 문제
[11989번: 断層 (Geologic Fault) (acmicpc.net)](https://www.acmicpc.net/problem/11989)

## 해설
전체를 45도 돌려서 생각하는 것이 편합니다. 45도 돌려서 지층이 이동하는 모습을 보면 가로와 세로 방향으로 이동하는 것이 됩니다.
### 서브테스크 1
지층이 이동하는 것을 직접 모두 구현해도 충분한 제한입니다. 쿼리를 모두 시뮬레이션하고 마지막 상태를 출력하면 됩니다. $O(N^2)$개의 칸만 저장하면 되며, 한 쿼리를 $O(N^2)$에 처리할 수 있어 $O(N^2Q)$에 18점을 얻을 수 있습니다.

### 서브테스크 2
쿼리를 거꾸로 처리하는 발상을 해봅시다. 그러면 다음과 같은 문제로 다시 쓰여집니다.
"침강이 Q번 일어난다. 지표면 좌표 1~N의 점은 Q번의 침강 후 어디로 가는가?
그러면 이동하는 영역의 포함된 모든 지층은 $x$좌표 또는 $y$좌표가 변하게 됩니다.
쿼리를 역순으로 보며 각 표면 지층의 위치를 갱신합니다. 각 쿼리마다 현재 움직이는 영역에 포함되는 표면 지층의 좌표를 움직입니다. 각 쿼리마다 $O(N)$에 처리할 수 있으므로, $O(NQ)$에 서브테스크 1의 점수를 합쳐 34점을 얻을 수 있습니다.

### 서브테스크 3
$x$좌표, 또는 $y$좌표를 바꾸는 것을 더 빠르게 처리합시다. 쿼리를 역순으로 처리할 때, 표면 지층들의 현재 위치의 $x$좌표의 단조성과 $y$좌표의 단조성이 항상 유지된다는 사실을 알 수 있습니다. 또한, 각 쿼리에서 위치를 바꿔야 하는 표면 지층은 $x$좌표가 어떤 값 이하인 영역 또는 $y$좌표가 어떤 값 이하인 영역에 포함되는 것입니다. 따라서 초기에 연속해 있던 표면 지층들에 대한 정보가 변합니다. 
처리하는 쿼리는 연속된 점들의 $x$좌표 또는 $y$좌표에 어떤 값을 더하거나 빼는 것입니다. 그러므로 구간 대한 쿼리를 처리하기 위해 Fenwick Tree나 Segment Tree와 같은 자료 구조를 사용할 수 있습니다. 
이제 남은 문제는 값을 더하는 구간을 찾는 것입니다. $x$좌표가 어떤 값 이하인 마지막 점 또는 $y$좌표가 어떤 값 이상인 첫 번째 점을 구하는데 이진 탐색을 사용할 수 있습니다. 이는 $O(\log^2N)$ 또는 Segment Tree에서의 이진 탐색을 통해 $O(\log N)$에 구할 수 있습니다. 따라서 전체 문제를 $O(Q\log N)$ 또는 $(Q\log^2 N)$에 해결할 수 있습니다.
