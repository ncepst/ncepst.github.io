[高周波特性1](RF_formula.md)  

## RFIC

■雑音指数NF (Noise Figure)  
入力にSN比(dB)に対して、出力のSN比(dB)がどの程度低下するかを示す量  

$$
\begin{aligned}
NF[dB]=入力のSN比[dB]-出力のSN比[dB] \\
F=\frac{\left(\frac{S}{N}\right)_{in}}{\left(\frac{S}{N}\right)_{out}}  >1
\end{aligned}
$$

■フリスの公式（多段増幅回路の雑音指数）  
${F_{\mathrm{total}}=F_1 + \frac{F_2 - 1}{G_1} + \frac{F_3 - 1}{G_1 G_2} + \frac{F_4 - 1}{G_1 G_2 G_3} + \cdots}$  
- 多段増幅回路では入力段の素子で雑音指数がほぼ決まる。  
- 初段の電力利得が十分に高ければ2段目以降の回路の雑音指数の影響を受けにくくなる。

■フリスの伝送公式  
${P_t:送信電力,　P_r:受信電力,　G_t:送信アンテナ効率,　G_r:受信アンテナ効率,　\lambda:波長,　R:送受信間距離}$  

$$
P_r= P_t G_t G_r \left( \frac{\lambda}{4\pi R} \right)^2
$$

アンテナ理論から、有効開口面積: ${A_e=\frac{G_r \lambda^2}{4 \pi}}$ となり、  
受信感度は ${\lambda^2}$ に比例する。

■リターンロス(Return Loss)  
${\mathrm{RL[dB]}=-20 \log_{10} \left| \Gamma \right|=20 \log_{10} \left(\frac{VSWR+1}{VSWR-1}\right)}$  
${\mathrm{RL[dB]}=-20 \log_{10} \left| S_{11} \right|}$  
反射0でRL=-∞

■透過率  
電圧波の透過率  
${\tau=1+\Gamma}$  

■挿入損失(Insertion Loss)  
電力の透過率  
ポート1からポート2への透過パラメータ ${S_{21}}$  
${\mathrm{IL[dB]}=-20 \log_{10}\left|S_{21}\right|}$  

アンプのゲイン  
${G \approx 20 \log_{10}\left|S_{21}\right|}$  

*損失がない場合  
${\left|S_{21}\right|^2+\left|S_{11}\right|^2=1}$  
${\mathrm{IL[dB]}=-10 \log_{10}(1-\left|\Gamma \right|^2)}$  
${T=1-\left|\Gamma \right|^2}$  

■相互変調歪み(IMD: Inter Modulatation Distortion)  
非線形な回路に2つ以上の異なる周波数の信号を入力すると、その和や差に対応する周波数成分が発生する  
2次歪み、3次歪み など

3次相互変調歪み(IM3)  
${2f_1-f_2,　2f_2-f_1}$  

アンプの入力電力[dBm]vs出力電力[dBm]を考えたとき、
入力電力に比例した電力で基本波を出力するのに対し、IM3は入力電力の3乗に比例して増加する。  
基本波(傾き1)とIM3(傾き3)の直線領域の線を延長し、交差した点をインターセプト(Intercept Point)と呼ぶ。  
入力電力(Input)で読むとIIP, 出力電力(Output)で読むとOIP  
増幅器の線形性(リニアリティ)を表す指標として用いられる。  

■位相雑音  
信号の瞬時位相が時間とともに乱れ、キャリア周辺のスペクトルにサイドバンドとして現れる雑音成分  

## デジタルフィルタ  
■FIRフィルタ(畳み込み): L＝タップ数,　h[k]=タップ係数(インパルス応答)

$$ 
y[n] = \sum_{k=0}^{L-1} h[k]x[n-k]  
$$

Z変換(伝達関数)

$$
Y(z)=H(z)X(z), \qquad
H(z)=\sum_{k=0}^{L-1} h[k]z^{-k} 
$$

周波数応答の公式  
z平面の単位円 ${z=e^{j \omega}}$ に代入:  

$$
H(e^{j\omega})=\sum_{k=0}^{L-1} h[k]e^{-j\omega k} 
$$

振幅特性: ${\left|H(e^{j\omega})\right|}$  
位相特性: ${\angle(H(e^{j\omega}))}$  

■IIRフィルタ(フィードバックあり): 

$$
y[n] = \sum_{k=0}^{M} b_kx[n-k] - \sum_{k=1}^{N} a_ky[n-k]
$$  

伝達関数は  ${Z[y[n]] = Y(z), \quad Z[x[n-k]] = z^{-k} X(z), \quad Z[y[n-k]] = z^{-k} Y(z)}$ を用いて、

$$
\begin{aligned}
Y(z) = \sum_{k=0}^{M} b_k z^{-k} X(z) - \sum_{k=1}^{N}  a_k z^{-k} Y(z) \\
Y(z) \left( 1+\sum_{k=1}^{N} a_k z^{-k} \right) = \left( \sum_{k=0}^{M} b_k z^{-k} \right) X(z) \\
H(z)=\frac{Y(z)}{X(z)}=\frac{\sum_{k=0}^{M} b_k z^{-k}}{1+\sum_{k=1}^{N} a_k z^{-k}}
\end{aligned}
$$

注)
- Z変換は畳み込みを掛け算に変える  
- 微分方程式→ラプラス変換、差分方程式→Z変換
-  ${z=e^{st}}$ : ラプラス領域は極が左平面で安定(収束)なのに対して、Z領域では 極が単位円内 で安定(収束)
- Z変換は ${z^n}$ をLTI(線形・時不変)系の固有関数, ${H(z)}$ をその固有値とし、LTI系を対角化している  

■DFE(Decision feedback equalizer):  

$$
y[n] = x[n]-\sum_{k} d_k\hat{x}[n-k]
$$  

---

## 電磁界解析(EM解析)
- MoM（モーメント法）：境界条件を元に積分方程式を解く  
${導体表面の表面電流密度 J と電荷を未知量とし、導体表面の接線方向の電界 E_{tan}=0 を境界条件とした定常状態での解を求める}$
${境界条件は、入射電界+放射電界=0 ⇒ 表面電流が作る電界が入射波を打ち消す E(J)=-E_{inc}}$  
- PEEC(Partial Element Equivalent Circuit)：等価回路で考える （準静的近似に基づく。寄生容量、寄生インダクタンスを考慮）      
- FEM(有限要素法)   
- FDTD(有限差分時間領域法)

---

## ハーモニックバランス法 (Harmonic Balance Method)

トランジェント解析が時間領域で微分方程式を直接解くのに対して、  
ハーモニックバランス法（HB法）は **周期定常解を仮定し、周波数領域を主として解く手法** である。

### 周期解の仮定

回路の周期解をフーリエ級数で表す：

$$
v(t) = \sum_{k=-N}^{N} V_k e^{j k \omega t}
$$

ここで

- $V_k$ ：高調波成分（未知数）
- $\omega$ ：基本角周波数
- $N$ ：考慮する高調波次数

HB法では、この **フーリエ係数 $V_k$ を未知数として解く。**


### 周波数領域でのKCL

各ノードにおいて、各周波数成分ごとにキルヒホッフの電流則（KCL）を立てる：

$$
I_{\mathrm{linear}}(k) + I_{\mathrm{nonlinear}}(k) = 0
$$

これをまとめると、非線形連立方程式

$$
F(\mathbf{V}) = 0
$$

となる。

ここで

$$
\mathbf{V} =
\begin{bmatrix}
V_{\omega} \\
V_{2\omega} \\
V_{3\omega} \\
\vdots
\end{bmatrix}
$$

は全高調波成分を含む未知数ベクトルである。


### 線形部分と非線形部分の違い

#### 線形回路

線形部分では各周波数成分は独立であり、

$$
I_k = Y(k\omega) V_k
$$

と書ける。

つまり、周波数ごとに独立に扱える。

#### 非線形回路

非線形素子では

$$
i(t) = f(v(t))
$$

となるため、例えば

$$
v(t) = V_1 \cos \omega t
$$

とすると、

$$
v^2(t) = \frac{V_1^2}{2}(1 + \cos 2\omega t)
$$

のように高調波が生成される。

したがって、

$$
I_k = f(V_{\omega}, V_{2\omega}, V_{3\omega}, \dots)
$$

となり、各高調波成分は互いに結合する。


### 数値解法（ニュートン法）

HB法では、

$$
F(\mathbf{V}) = 0
$$

をニュートン法により解く。

多変数ニュートン法は

$$
\mathbf{V}_{\text{new}} = \mathbf{V} - \mathbf{J}^{-1} F(\mathbf{V})
$$

ここで

$$
\mathbf{J} = \frac{\partial F}{\partial \mathbf{V}}
$$

はヤコビアン行列である。

この反復計算を収束するまで繰り返す。


### まとめ

- 周期定常解をフーリエ級数で仮定する  
- フーリエ係数を未知数とする  
- 各周波数成分ごとにKCLを立てる  
- 非線形により高調波は相互に結合する  
- 巨大な非線形代数方程式をニュートン法で解く  

ハーモニックバランス法は、  
時間領域の微分方程式を直接解くのではなく、  
**フーリエ空間上で周期解を直接求める手法**である。


[高周波特性1](RF_formula.md)  
[L型マッチング回路](L_matching.md)  

[ホームに戻る](index.md)  
