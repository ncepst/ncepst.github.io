# RF公式

表皮深さ(skin depth)  
${\delta=\sqrt{\frac{2 \rho}{\omega \mu}}}$  
⇒ ${\sqrt{f}}$に反比例する    
導体抵抗は断面積(表皮深さ)に反比例するため、導体損は ${\sqrt{f}}$ に比例する。　　  
同軸ケーブルには導体損と誘電体損があるが、1GHzを十分に下回る周波数では導体損が支配的。 

低周波では導体損失が支配的である一方で、高周波では誘電体損失が支配的になる。  
誘電正接は、誘電体に蓄えられたエネルギーに対して失われるエネルギーの比率で表されます。  
また、GNDに対するRCの並列回路を考えて、コンデンサに流れる電流に対する寄生抵抗に流れる電流と等しくなります。  
誘電正接 ${tan𝛿=\frac{誘電体損失(失われるエネルギー)}{蓄積される電界エネルギー}=\frac{寄生抵抗に流れる電流}{理想コンデンサに流れる電流}=\frac{1}{\omega CR}=\frac{G}{\omega C}}$  
漏れコンダクタンス ${G=\omega C \tan{\delta}=\omega \varepsilon \frac{A}{d} \tan{\delta}}$  
誘電体損失は、周波数f、誘電率ε、誘電正接tanδに比例します。  

​
特性インピーダンス  
${Z_0=\sqrt{\frac{R+j\omega L}{G+j\omega C}}}$  

R：単位長さあたりの抵抗 → 導体損失（ジュール損失）  
G：単位長さあたりのコンダクタンス → 誘電体損失（漏れコンダクタンス）  

低損失線路近似  
${Z_0=\sqrt{\frac{L}{C}}}$  

伝搬定数  ${\gamma =\sqrt{(R+j\omega L)(G+j\omega C)}}$  

伝送線路には 導体損失（抵抗 R）と 誘電体損失（漏れコンダクタンス G）があり、    
低損失線路近似では、  
減衰定数 ${\alpha \approx \alpha_c + \alpha_d}$  
導体損 ${\alpha_c= \frac{1}{2}\frac{R}{Z_0}=\frac{R}{2}\sqrt{\frac{C}{L}}}$   
​
誘電体損 ${\alpha_d= \frac{1}{2}GZ_0=\frac{G}{2}\sqrt{\frac{L}{C}}}$  
位相定数 ${\beta=\omega \sqrt{LC}}$
  


反射係数  
${\Gamma=\frac{Z_L-Z_0}{Z_L+Z_0}}$  
スミスチャートでは原点からの距離が| ${\Gamma}$ | 

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
${Z=\sqrt{\frac{\mu_0}{\varepsilon_0}}=377 \Omega}$  

位相速度: 波数kに対する角周波数  
${v_p=\frac{\omega}{\beta}=\frac{1}{\sqrt{LC}}}$  

LとCの幾何学項が打ち消しあう場合  
${v_p=\frac{\omega}{\beta}=\frac{1}{\sqrt{\varepsilon \mu}}}$  
真空中では  
${v_p=\frac{1}{\sqrt{\varepsilon_0 \mu_0}}=c}$

群速度:  
${v_g=\frac{d\omega}{d\beta}}$ 

結合線路の結合係数k    
${k=\frac{Z_{even}-Z_{odd}}{Z_{even}+Z_{odd}}}$  
近端クロストーク　NEXT≈ $${k}$$  
遠端クロストーク　FEXT≈ $${k \Delta v}$$   ( ${\Delta v = v_{even}-v_{odd}}$)  
