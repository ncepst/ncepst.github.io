CMOSオペアンプ設計入門: CMRR・PSRR・カスコード化

アナログIC設計を学び始めると必ず出てくる「CMRR」「PSRR」「カスコード化」。本記事では、差動対の小信号解析から CMRR ≈ gm·ro_tail が現れる理由、カスコード化がなぜ有効なのか、Fully Differential OPAMPとの関係まで整理する。

CMRRとは何か
CMRR（Common Mode Rejection Ratio）は、

同相入力をどれだけ除去できるか

を表す指標である。

定義は

C
M
R
R
=
A
d
A
c
m
CMRR= 
A 
cm
​
 
A 
d
​
 
​
 
である。

ここで、

A
d
A 
d
​
 ：差動利得
A
c
m
A 
cm
​
 ：同相利得
である。

CMRRが大きいほど、

電源ノイズ
基板ノイズ
同相干渉
の影響を受けにくい。

同相信号とは
差動入力が

v
i
d
=
v
i
n
+
−
v
i
n
−
v 
id
​
 =v 
in+
​
 −v 
in−
​
 
であるのに対し、

同相信号は

v
i
n
+
=
v
i
n
−
=
v
c
m
v 
in+
​
 =v 
in−
​
 =v 
cm
​
 
である。

例えば

v
i
n
+
=
1.2
V
+
1
m
V
sin
⁡
ω
t
v 
in+
​
 =1.2V+1mVsinωt
v
i
n
−
=
1.2
V
+
1
m
V
sin
⁡
ω
t
v 
in−
​
 =1.2V+1mVsinωt
であれば、

1mVの正弦波が同相信号である。

CMRR解析では、この微小交流信号を扱う。

差動対の基本構成


          VDD
           |
         RD   RD
           |   |
          M1   M2
           \   /
            \ /
             ●
             |
          Itail
             |
            GND
なぜ同相信号でソース電位が動くのか
入力を100mV上げると、



Gate ↑
↓
電流が増えようとする
↓
ソース電位も上昇
↓
VGSが元へ戻る
という負帰還が働く。

理想的なテイル電流源なら、

V
S
≈
V
C
M
V 
S
​
 ≈V 
CM
​
 
となり、

V
G
S
V 
GS
​
 
はほぼ一定である。

したがって出力は変化しない。

CMRRが有限になる原因
原因は

r
o
,
t
a
i
l
r 
o,tail
​
 
が有限であることである。

MOS電流源は

I
D
=
I
0
(
1
+
λ
V
D
S
)
I 
D
​
 =I 
0
​
 (1+λV 
DS
​
 )
であり、

V
D
S
V 
DS
​
 
が変わると電流も変化する。

同相信号でソース電位が上昇すると、

テイル電流源の

V
D
S
V 
DS
​
 
が変化し、

I
t
a
i
l
I 
tail
​
 
も変化する。

結果として出力が変化する。

同相利得の導出
小信号で

v
s
v 
s
​
 
をソースノード電圧とする。

各MOSの電流変化は

i
d
=
g
m
(
v
c
m
−
v
s
)
i 
d
​
 =g 
m
​
 (v 
cm
​
 −v 
s
​
 )
である。

左右合わせると

2
g
m
(
v
c
m
−
v
s
)
=
v
s
r
o
,
t
a
i
l
2g 
m
​
 (v 
cm
​
 −v 
s
​
 )= 
r 
o,tail
​
 
v 
s
​
 
​
 
となる。

整理すると

v
s
=
2
g
m
r
o
,
t
a
i
l
1
+
2
g
m
r
o
,
t
a
i
l
v
c
m
v 
s
​
 = 
1+2g 
m
​
 r 
o,tail
​
 
2g 
m
​
 r 
o,tail
​
 
​
 v 
cm
​
 
となる。

通常は

g
m
r
o
,
t
a
i
l
≫
1
g 
m
​
 r 
o,tail
​
 ≫1
なので

v
s
≈
v
c
m
v 
s
​
 ≈v 
cm
​
 
である。

残るゲートソース電圧変化は

v
g
s
=
v
c
m
−
v
s
v 
gs
​
 =v 
cm
​
 −v 
s
​
 
≈
v
c
m
2
g
m
r
o
,
t
a
i
l
≈ 
2g 
m
​
 r 
o,tail
​
 
v 
cm
​
 
​
 
である。

そのため

i
d
=
g
m
v
g
s
=
v
c
m
2
r
o
,
t
a
i
l
i 
d
​
 =g 
m
​
 v 
gs
​
 = 
2r 
o,tail
​
 
v 
cm
​
 
​
 
となる。

出力電圧は

v
o
=
−
i
d
R
D
v 
o
​
 =−i 
d
​
 R 
D
​
 
であるから、

A
c
m
=
v
o
v
c
m
=
−
R
D
2
r
o
,
t
a
i
l
A 
cm
​
 = 
v 
cm
​
 
v 
o
​
 
​
 =− 
2r 
o,tail
​
 
R 
D
​
 
​
 
となる。

差動利得
差動入力

v
i
d
v 
id
​
 
を与えると、

片側出力では

A
d
=
−
g
m
R
D
2
A 
d
​
 =− 
2
g 
m
​
 R 
D
​
 
​
 
である。

CMRRの導出
定義より

C
M
R
R
=
∣
A
d
∣
∣
A
c
m
∣
CMRR= 
∣A 
cm
​
 ∣
∣A 
d
​
 ∣
​
 
である。

代入すると

C
M
R
R
=
g
m
R
D
2
R
D
2
r
o
,
t
a
i
l
CMRR= 
2r 
o,tail
​
 
R 
D
​
 
​
 
2
g 
m
​
 R 
D
​
 
​
 
​
 
C
M
R
R
=
g
m
r
o
,
t
a
i
l
CMRR=g 
m
​
 r 
o,tail
​
 
となる。

このgmはどこのgmか
重要なポイントである。

C
M
R
R
=
g
m
r
o
,
t
a
i
l
CMRR=g 
m
​
 r 
o,tail
​
 
に現れる 
g
m
g 
m
​
  は

入力差動対(M1/M2)のgm

である。

テイルトランジスタのgmではない。

この式が適用される範囲
この式は



差動対
+
対称負荷
+
Tail電流源
のみを考えた一次近似である。

つまり、



      RD       RD
       |       |
      M1       M2
       \       /
        \     /
         \   /
        Itail
のCMRRである。

能動負荷があるとどうなるか
実際のCMOS OPAMPは



      PMOS Current Mirror
          |
          |
      M1     M2
         \ /
        Itail
のような構成になる。

この場合、

CMRRは

g
m
r
o
,
t
a
i
l
g 
m
​
 r 
o,tail
​
 
だけでは決まらない。

効くものとして

テイル電流源のro
PMOS負荷のro
PMOS負荷のミスマッチ
電流ミラー誤差
バイアス回路
などがある。

PMOS能動負荷のroはCMRRに効くのか
答えはYESである。

有限の

r
o
,
p
r 
o,p
​
 
を持つと

同相信号による電流変化が

出力電圧へ変換される。

よって

A
c
m
A 
cm
​
 
が増加し、

CMRRを悪化させる。

PSRRとは
PSRR(Power Supply Rejection Ratio) は

P
S
R
R
=
Δ
V
s
u
p
p
l
y
Δ
V
o
u
t
PSRR= 
ΔV 
out
​
 
ΔV 
supply
​
 
​
 
で定義される。

電源変動が出力へ漏れる割合である。

カスコード化の本質
カスコード化の主目的は

r
o
を大きくすること
r 
o
​
 を大きくすること
​
 
である。

通常の電流源



VDD
 |
M1
 |
out
では

r
o
≈
1
λ
I
D
r 
o
​
 ≈ 
λI 
D
​
 
1
​
 
である。

カスコード化すると



VDD
 |
Mcas
 |
M1
 |
out
となる。

すると

r
o
,
c
a
s
≈
g
m
r
o
2
r 
o,cas
​
 ≈g 
m
​
 r 
o
2
​
 
まで増加する。

なぜroが増えるのか
カスコードMOSが

下段MOSの

V
D
S
V 
DS
​
 
をほぼ一定に保つからである。

結果として

チャネル長変調低減
電流変動低減
高出力抵抗化
が実現する。

カスコード化のメリット
1. DCゲイン向上
アンプ利得は

A
v
≈
g
m
R
o
u
t
A 
v
​
 ≈g 
m
​
 R 
out
​
 
である。

出力抵抗が増えるため

A
v
A 
v
​
 
が増加する。

2. CMRR向上
C
M
R
R
≈
g
m
r
o
,
t
a
i
l
CMRR≈g 
m
​
 r 
o,tail
​
 
より

r
o
,
t
a
i
l
↑
r 
o,tail
​
 ↑
なら

C
M
R
R
↑
CMRR↑
となる。

3. PSRR向上
電源変動による

Δ
I
ΔI
が減少する。

したがってPSRRが向上する。

4. Miller効果低減
下段MOSのドレイン電圧がほぼ固定される。

その結果

C
g
d
C 
gd
​
 
のMiller増幅が大きく減少する。

高速回路では非常に重要である。

5. 電流ミラー精度向上
ミラー対の

V
D
S
V 
DS
​
 
を揃えやすくなる。

よって

I
o
u
t
≃
I
r
e
f
I 
out
​
 ≃I 
ref
​
 
となる。

カスコードノードとは
例えば



VDD
 |
Mcas
 |
● Vx
 |
M1
 |
GND
の

V
x
V 
x
​
 
である。

McasとM1の接続点を指す。

カスコードノードは固定されるのか
完全には固定されない。

しかし、

R
x
≈
1
g
m
,
c
a
s
R 
x
​
 ≈ 
g 
m,cas
​
 
1
​
 
となるため、

かなり低インピーダンスになる。

例えば

g
m
=
10
m
S
g 
m
​
 =10mS
なら

R
x
=
100
Ω
R 
x
​
 =100Ω
程度しかない。

そのため

V
x
V 
x
​
 
はほとんど動かない。

なぜ極(Pole)が増えるのか
よくある誤解は

MOSが1個増えるとPoleが1個増える

である。

そうではない。

極が増える理由は

内部ノードが増えるから

である。



VDD
 |
Vo
 |
Mcas
 |
Vx
 |
M1
 |
GND
では

Vo
Vx
という2つの状態変数が存在する。

それぞれに容量がぶら下がるため

p
o
p 
o
​
 
と

p
x
p 
x
​
 
が発生する。

カスコードノードの極は高周波
カスコードノードは

R
x
≈
1
g
m
R 
x
​
 ≈ 
g 
m
​
 
1
​
 
で小さい。

そのため

f
x
=
1
2
π
R
x
C
x
f 
x
​
 = 
2πR 
x
​
 C 
x
​
 
1
​
 
は非常に高くなる。

例えば

R
x
=
100
Ω
R 
x
​
 =100Ω
C
x
=
100
f
F
C 
x
​
 =100fF
なら

f
x
≈
16
G
H
z
f 
x
​
 ≈16GHz
である。

そのため実用帯域から十分離れることが多い。

片側出力とは何か
差動対は出力を2つ持つ。



Vo+      Vo-
 |         |
M1        M2
 \        /
  Itail
片側出力とは

V
o
u
t
=
V
o
+
V 
out
​
 =Vo+
のみを観測することを意味する。

差動出力なら

V
o
u
t
=
V
o
+
−
V
o
−
V 
out
​
 =Vo+−Vo−
となる。

Single-Ended OPAMPとの違い
Single-Ended OPAMP



差動入力
   ↓
差動対
   ↓
単一出力化
   ↓
Vout
出力端子は1本。

Fully Differential OPAMP



差動入力
   ↓
増幅
   ↓
Vo+
Vo-
出力端子は2本。

CMRR ≈ gm·rotail は何の式か
最終整理すると、

C
M
R
R
≈
g
m
r
o
,
t
a
i
l
CMRR≈g 
m
​
 r 
o,tail
​
 
​
 
は

入力差動対単体のCMRR

を表す一次近似式である。

これは

Single-Ended OPAMPでも使う
Fully Differential OPAMPでも使う
ただし、

オペアンプ全体のCMRRを表しているわけではない。

設計者視点でのまとめ
CMRRを改善したいときは、

まず

r
o
,
t
a
i
l
r 
o,tail
​
 
を見る。

つまり



CMRRが低い
↓
Tail電流源をカスコード化
↓
ro向上
↓
CMRR向上
である。

また能動負荷の

r
o
r 
o
​
 
も

DCゲイン
PSRR
CMRR
すべてに効く。

そのため高性能CMOS OPAMPでは、

Tail電流源カスコード
PMOS負荷カスコード
高ゲインバイアス
が頻繁に使われる。

参考として覚えるべき式
A
d
=
g
m
R
D
2
A 
d
​
 = 
2
g 
m
​
 R 
D
​
 
​
 
A
c
m
=
R
D
2
r
o
,
t
a
i
l
A 
cm
​
 = 
2r 
o,tail
​
 
R 
D
​
 
​
 
C
M
R
R
=
g
m
r
o
,
t
a
i
l
CMRR=g 
m
​
 r 
o,tail
​
 
A
v
=
g
m
R
o
u
t
A 
v
​
 =g 
m
​
 R 
out
​
 
r
o
,
c
a
s
≈
g
m
r
o
2
r 
o,cas
​
 ≈g 
m
​
 r 
o
2
​
 
アナログ回路設計では、これら5式だけでもCMRR・PSRR・カスコード化の本質のかなりの部分を理解できる。
