# RF公式

表皮深さ(skin depth)  
${\delta=\sqrt{\frac{2 \rho}{\omega \mu}}}$  
⇒ ${\sqrt{f}}$に反比例する    
導体抵抗は断面積(表皮深さ)に反比例するため、導体損は ${\sqrt{f}}$ に比例する。　　  
同軸ケーブルには導体損と誘電体損があるが、1GHzを下回る周波数では導体損が支配的。 

低周波では導体損失が支配的である一方で、高周波では誘電体損失が支配的になる。  
誘電体損失は、誘電体に蓄えられたエネルギーに対して失われるエネルギーの比率で表されます  
誘電正接 tan𝛿=　誘電体損失（エネルギー消費）÷ 蓄積される電界エネルギー = ${\omega CR}$  
漏れコンダクタンス ${G=\omega C \tan{\delta}=\omega \varepsilon \frac{A}{d} \tan{\delta}}$

​
特性インピーダンス  
${Z_0=\sqrt{\frac{R+j\omega L}{G+j\omega C}}}$  

R：単位長さあたりの抵抗 → 導体損失（ジュール損失）  
G：単位長さあたりのコンダクタンス → 誘電体損失（漏れコンダクタンス）  

低損失線路近似  
${Z_0=\sqrt{\frac{L}{C}}}$  

伝搬定数  ${\gamma =\sqrt{(R+j\omega L)(G+j\omega C)}}$

反射係数  ${\Gamma=\frac{Z_L-Z_0}{Z_L+Z_0}}$

定在波比  
${VSWR=\frac{V_{max}+V_{min}}{V_{max}-V_{min}}}$  
${VSWR=\frac{1+|\Gamma|}{1-|\Gamma|}}$  
${VSWR=\frac{\sqrt{P_f}+\sqrt{P_r}}{\sqrt{P_f}-\sqrt{P_r}}}$  

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
