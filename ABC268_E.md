```
4
1 2 0 3
```

| 0     | 1     | 2    | 3    | $sum$ |
| ----- | ----- | ---- | ---- | ----- |
| 1(-1) | 2(-1) | 0(2) | 3(0) | 4     |
| 3(1)  | 1(0)  | 2(0) | 0(3) | 2     |
右周りにどれくらい離れているかを距離として定義

|         | 1    | 2    | 0    | 3    | $sum$ |
| ------- | ---- | ---- | ---- | ---- | ----- |
| 0 1 2 3 | 3(-) | 3(-) | 2(-) | 0(+) | 4     |
| 1 2 3 0 | 0(+) | 0(+) | 3(-) | 1(+) | 2     |
| 2 3 0 1 | 1(+) | 1(+) | 0(+) | 2(-) | 4     |
| 3 0 1 2 | 2(-) | 2(-) | 1(+) | 3(-) |       |
次のような二項演算はセグ木に乗るか？__乗らない__。却下。
$$
a, b \in Z\ Mod\ N 
$$
$$
op(a, b)=min(a,N-a)+min(b,N-b)
$$
$$
e=0
$$

$+$になる要素と$-$ になる要素の数だけ分かればよい。
数iの距離a回転後の距離を$dist(i, a)$とする。ここで、
$0\le dist(i,a)\lt N$
たとえば、$N=5$ のとき、取りうる距離は$0,1,2,3,4$
たとえば、$N=4$ のとき、取りうる距離は$0,1,2,3$
ある$i$について、$dist(i, 0)=d_i$ であったとする。
このとき、$dist(i,a)=(d_i-a) \ mod\ N$
$dist(i, a)\lt dist(i, a + 1)$となるのは、$0\le dist(i, a)\lt \lfloor\frac{N}{2}\rfloor$のときで、
$dist(i, a)\gt dist(i, a + 1)$となるのは、$\lfloor\frac{N+1}{2}\rfloor \le dist(i, a) \lt N$のとき。

つまり、
$dist(i, a)\lt dist(i, a + 1)$となるのは、$0\le (d_i-a)\ mod \ N\lt \lfloor\frac{N}{2}\rfloor$のときで、
$dist(i, a)\gt dist(i, a + 1)$となるのは、$\lfloor\frac{N+1}{2}\rfloor \le (d_i-a)\ mod \ N \lt N$のとき。
