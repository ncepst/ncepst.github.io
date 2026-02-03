# RF公式

表皮深さ(skin depth)  
${\delta=\sqrt{\frac{2 \rho}{\omega \mu}}}$  
⇒ ${\sqrt{f}}$に反比例する    
導体抵抗は断面積(表皮深さ)に反比例するため、導体損は ${\sqrt{f}}$ に比例する。　　  
同軸ケーブルには導体損と誘電体損があるが、1GHzを十分に下回る周波数では導体損が支配的。  
また、電磁波が導体内部に浸透する長さも表皮深さで決まり、δの数倍の厚みの導体で囲むことで、  
外部電磁波を遮る効果があります(ファラデーゲージ)。  

伝送線路において、低周波では導体損失が支配的である一方で、高周波では誘電体損失が支配的になります。  
誘電正接は、誘電体に蓄えられたエネルギーに対して失われるエネルギーの比率で表されます。  
また、GNDに対するRCの並列回路を考えて、コンデンサに流れる電流に対する寄生抵抗に流れる電流と等しくなります。  
誘電正接 ${tan𝛿=\frac{誘電体損失(失われるエネルギー)}{蓄積される電界エネルギー}=\frac{寄生抵抗に流れる電流}{理想コンデンサに流れる電流}=\frac{1}{\omega CR}=\frac{G}{\omega C}}$  
漏れコンダクタンス ${G=\omega C \tan{\delta}=\omega \varepsilon \frac{A}{d} \tan{\delta}}$  
誘電体損失は、周波数f、誘電率ε、誘電正接tanδに比例します。  

​
分布定数回路の特性インピーダンス  
${Z_0=\sqrt{\frac{R+j\omega L}{G+j\omega C}}}$  

R：単位長さあたりの抵抗 → 導体損失（ジュール損失）  
G：単位長さあたりのコンダクタンス → 誘電体損失（漏れコンダクタンス）  

低損失線路近似  
${Z_0=\sqrt{\frac{L}{C}}}$  

伝搬定数  ${\gamma =\sqrt{(R+j\omega L)(G+j\omega C)}}$  
    
低損失線路近似では、  
減衰定数 ${\alpha \approx \alpha_c + \alpha_d}$  
導体損失 ${\alpha_c= \frac{1}{2}\frac{R}{Z_0}=\frac{R}{2}\sqrt{\frac{C}{L}}}$   
​
誘電体損失 ${\alpha_d= \frac{1}{2}GZ_0=\frac{G}{2}\sqrt{\frac{L}{C}}∝ f\cdot\tan{\delta}\cdot\sqrt{\varepsilon_r}}$  
位相定数 ${\beta=\omega \sqrt{LC}}$
  


反射係数  
${\Gamma=\frac{Z_L-Z_0}{Z_L+Z_0}}$  
スミスチャートでは原点からの距離が ${\left| \Gamma \right|}$  

Sパラメータ(散乱パラメータ)  
　入射する電力波の複素振幅に対する、反射・透過する電力波の複素振幅の比  
　 ${S_{ij}=\frac{b_i}{a_j}}$    
　計算では、複素振幅 ${Ae^{j(\omega t-\beta z)}}$ で時間変動を無視して、(=時間依存項 ${Ae^{j\omega t}}$ を無視)  
　位置に対する振幅(包絡線)と位相で考える。  
　入力電力、反射電力、透過電力は、Sパラメータの絶対値の2乗 ${\left|S_{ij}\right|^2}$ で計算される。  
　複素数の加算で電力を求める場合、 ${\left| a+b \right|^2= \left|a \right|^2+\left|b \right|^2+2Re(ab^*)}$ を用いる。  


定在波比  
${VSWR=\frac{V_{max}+V_{min}}{V_{max}-V_{min}}}$  
${VSWR=\frac{1+|\Gamma|}{1-|\Gamma|}}$  
${VSWR=\frac{\sqrt{P_f}+\sqrt{P_r}}{\sqrt{P_f}-\sqrt{P_r}}}$  
VSWRは1~∞の値となり、VSWR=1.5で損失は4%  
(スミスチャートでは、円の下側に目盛がある)   

入力インピーダンス  
${Z_{in}=Z_0\frac{Z_L+Z_0tanh(\gamma l)}{Z_0+Z_Ltanh(\gamma l)}}$  

無損失線路 ${\alpha=0}$ では、  
${Z_{in}=Z_0\frac{Z_L+Z_0jtan(\beta l)}{Z_0+Z_Ljtan(\beta l)}}$  

${l=\frac{\lambda}{4}}$ では、 ${\lambda/4}$ インピーダンス変換器となり、    
${Z_{in}=\frac{Z_0^2}{Z_L}}$

波動インピーダンス (電波インピーダンス)  
${Z=\frac{|E|}{|H|}}$  

媒質の固有インピーダンス  
${Z=\sqrt{\frac{\mu}{\varepsilon}}}$  

${\mu}$が上がると、磁場を作りにくくなる。磁気抵抗が大きいため。  
( ${B=\mu H}$ なので、 ${B}$ 一定では磁場を作る能力の硬さのような指標)

${\varepsilon}$が上がると、電場を作りにくくなる。電気抵抗(誘電抵抗)が大きいため。  
( ${D=\varepsilon E}$ なので、 ${D}$一定では電場を作る能力の硬さのような指標)  

自由空間では、  
${Z_0=\sqrt{\frac{\mu_0}{\varepsilon_0}}=377 \Omega　(120\pi )}$  

位相速度: 波数kに対する角周波数  
${v_p=\frac{\omega}{\beta}=\frac{1}{\sqrt{LC}}}$  

LとCの幾何学項が打ち消しあう場合  
${v_p=\frac{\omega}{\beta}=\frac{1}{\sqrt{\varepsilon \mu}}}$  
真空中では  
${v_p=\frac{1}{\sqrt{\varepsilon_0 \mu_0}}=c}$  
光の屈折率nは  
${n=\frac{c}{v_p}=\sqrt{\varepsilon_r \mu_r}}$  
非磁性媒質での波動インピーダンス  
${Z=\sqrt{\frac{\mu_0}{\varepsilon}}=\frac{Z_0}{n}}$    
垂直入射での光の反射率  
${R=\left(\frac{n_1-n_2}{n_1+n_2}\right)^2}$  
ポインティングベクトル(平均電力密度)  
${\<S\>=\<E \times H\>=\frac{E_{\mathrm{rms}}^2}{Z}=\frac{GP}{4\pi r^2} [W/m^2]}$  
Gはアンテナゲイン ${G(\theta, \phi)}$  

Siの比誘電率:11.7  
SiO2 屈折率(光学領域):1.46, 比誘電率(RF領域):3.8～4.0  
Si3N4 屈折率(光学領域):2.00, 比誘電率(RF領域):7～8  
イオン分極・双極子分極が RF では大きく寄与するため、比誘電率が大きくなる。  
共有結合の強いSiでは、RFと光学で比誘電率が近い値になる。  

群速度:  
${v_g=\frac{d\omega}{d\beta}}$  
周波数応答 ${H(\omega)=\left|H(\omega)\right|e^{j \phi(\omega)}}$ の群遅延    
${\tau_g=-\frac{d\phi(\omega)}{d\omega}}$  

偶インピーダンス ${Z_{even}}$ :2本の線路に同じ大きさ・同じ位相で励振したときの1本あたりのモード特性インピーダンス    
奇インピーダンス ${Z_{odd }}$ :2本の線路に同じ大きさ・逆の位相で励振したときの1本あたりのモード特性インピーダンス  
結合線路の結合係数k    
${k=\frac{Z_{even}-Z_{odd}}{Z_{even}+Z_{odd}}}$  
近端クロストーク　NEXT≈ $${k}$$  
遠端クロストーク　FEXT≈ $${k \Delta v}$$   ( ${\Delta v = v_{even}-v_{odd}}$)  

磁気結合係数 ${k_L=\frac{M}{\sqrt{L_1L_2}}　(-1≦k_L≦1)}$  
容量結合係数 ${k_C=\frac{C_{12}}{\sqrt{C_1C_2}}　(0≦k_C<1)}$  

対称線路では、 ${C_{11}=C_{22},　L_{11}=L_{22}}$ であり、  
近端クロストーク　NEXT= ${\frac{1}{4}\left(\left|\frac{C_{12}}{C_{11}}\right|+\frac{L_{12}}{L_{11}}\right)}$  
遠端クロストーク　FEXT= ${\frac{l}{T_r}\frac{T_d}{2}\left(\left|\frac{C_{12}}{C_{11}}\right|-\frac{L_{12}}{L_{11}}\right)}$  
　(遅延時間 ${T_d=\sqrt{L_{11}C_{11}}}$,　立ち上がり時間 ${T_r}$ ,　配線長 ${l}$ )  


4つの基本的な電磁結合メカニズム  
・伝導結合(共通インピーダンス結合)  
・電界結合(容量結合)  
・磁界結合(誘導結合)  
・放射結合(遠方界結合) ：波長よりも十分に長い距離。放射源の導体長もλ/10以上。

不平衡度  
・電流分配率から定義される  
・ ${h=\frac{I_1}{I_1+I_2}}$  
・平衡線路ではh=0.5となる。  
・平衡線路と不平衡線路をつなげるとコモンモード電流(電流の同相成分)が励起されノイズの原因となる  
・ ${\Delta V_C=\Delta hV_N}$  

デジタルフィルタ  
FIRフィルタ(畳み込み): L＝タップ数,　h[k]=タップ係数(インパルス応答)

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

IIRフィルタ(フィードバックあり): 

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
- Z変換は ${z^n}$ をLTI(線形・時不変)系の固有関数, ${H(z)}$ をその固有値とし、LTI系を対角化している  

DFE(Decision feedback equalizer):  

$$
y[n] = x[n]-\sum_{k} d_k\hat{x}[n-k]
$$  
