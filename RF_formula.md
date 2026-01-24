# RF関連

表皮深さ(skin depth)  
${\delta=\sqrt{\frac{2 \sigma}{\omega \mu}}}$  
⇒ ${\sqrt{f}}$に反比例する

特性インピーダンス  
${Z_0=\sqrt{\frac{R+j\omega L}{G+j\omega C}}}$  

伝搬定数  ${\gamma =\sqrt{(R+j\omega L)(G+j\omega C)}}$

反射係数  ${\Gamma=\frac{Z_L-Z_0}{Z_L+Z_0}}$

定在波比  
${VSWR=\frac{V_{max}+V_{min}}{V_{max}-V_{min}}}$  
${VSWR=\frac{1+|\Gamma|}{1-|\Gamma|}}$  
${VSWR=\frac{\sqrt{P_f}+\sqrt{P_r}}{\sqrt{P_f}-\sqrt{P_r}}}$  

入力インピーダンス  
${Z_{in}=Z_0\frac{Z_0+Z_Ltanh(\gamma l)}{Z_L+Z_0tanh(\gamma l)}}$  

${\alpha=0}$ では、  
${Z_{in}=Z_0\frac{Z_0+Z_Ljtan(\beta l)}{Z_L+Z_0jtan(\beta l)}}$  

${l=\frac{\lambda}{4}}$ では、  
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
${Z=\sqrt{\frac{\mu_0}{\varepsilon_0}}=377 \ohm}$  

位相速度: 波数kに対する角周波数  
${v_p=\frac{\omega}{\beta}=\frac{1}{\sqrt{LC}}}$  

LとCの幾何学項が打ち消しあう場合  
${v_p=\frac{\omega}{\beta}=\frac{1}{\sqrt{\varepsilon \mu}}}$  
真空中では  
${v_p=\frac{1}{\sqrt{\varepsilon_0 \mu_0}}=c}$

群速度:  
${v_g=\frac{d\omega}{d\beta}}$ 
