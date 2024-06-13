- `<><`
- e.g. `1 5 3 4`
- 挿入のしかたを考える
- `10 20` のように幅を持って構築していくことを考える
- 挿入のしかたは$0\lt n \lt 10$ または $10 \lt n \lt 20$ 以下
- パーティションの入れ方は2つ
- $dp[n][ins]:=n$個目の要素を小さい要素から数えて何番目の位置に挿入するか
$$
dp[0][0]=1
$$

$$
dp[n][ins]=
	\begin{cases} 
		\sum_{ins\prime \ge ins} dp[n-1][ins\prime ] & (S[i] == '>') \\
		\sum_{ins\prime \lt ins} dp[n-1][ins\prime ] & (S[i] == '<') \
	\end{cases}
$$