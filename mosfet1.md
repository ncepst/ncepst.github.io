基本式

$$ I = q N v S $$

電荷密度はゲート酸化膜容量によって誘起される(誘起電荷)

$$ qN = C_{ox}(V_{GS} - V_{th}) 　- ①$$

N-MOSの電流密度：

$$ J = q N \mu_n E 　- ②$$

チャネル電位分布 ${V(0)=0,　V(L)=V_{DS}}$

チャネル内の電荷分布

チャネル位置 ${x}$ における電荷密度（W方向の電荷密度）：

$$ qN(x) = C_{ox}(V_{GS} - V_{th} - V(x)) 　- ③$$

チャネル位置 ${x}$ における電流密度（W方向の電流密度）：

$$ J(x) = C_{ox}(V_{GS} - V_{th} - V(x)) \mu_n \frac{dV(x)}{dx}  　- ④$$

ドレイン電流の導出

電荷量は はチャネル位置 ${x}$ に依存するが、電流連続を満たす必要があるので、  
${v=\mu E = \mu \frac{dV(x)}{dx}}$ が チャネル位置 ${x}$ に依存し、  
電荷の少ない箇所ほど速度が早くなる。  

チャネル長の短い、微小トランジスの直列接続と考え、
単位長さあたりのゲート容量 ${C_{ox}/L}$ で考える。

電流密度は  ${x=0}$ から ${x=L}$ までの積分と考えて、
さらに、電流はW方向の電流密度を ${W}$ 倍した値であることから、

$$ I_D = \mu_n C_{ox} \frac{W}{L} \left[(V_{GS}-V_{th})V_{DS} - \frac{1}{2}V_{DS}^2\right]   　- ⑤$$

もしくは単に④式の両辺を ${x=0}$ から ${x=L}$ までの積分しても求まる。

${\beta_n = \mu_n C_{ox} \frac{W}{L}}$ とおくと、

$$ I_D = \beta_n \left[(V_{GS}-V_{th})V_{DS} - \frac{1}{2}V_{DS}^2\right] $$

${I_D}$ が ${V_{DS}}$ について飽和する条件： ${\frac{\partial I_D}{\partial V_{DS}}=0}$ から、  
ピンチオフとなる条件が、⑤式の両辺を ${V_{DS}}$ で微分して0であるため、

ピンチオフ条件：

$$ V_{DSsat} = V_{GS} - V_{th}   　- ⑥$$

飽和電流：

$$ I_{Dsat} = \frac{1}{2}\mu_n C_{ox}\frac{W}{L}(V_{GS}-V_{th})^2$$
$$ I_{Dsat} = \frac{\beta_n}{2} (V_{GS}-V_{th})^2   　- ⑦$$

ドレイン電流 ${I_D}$を流すために必要な ${V_{gs}}$ ：

$$ V_{GS}=V_{th} + \sqrt{\frac{2I_D}{\beta}}    　- ⑧$$

これは閾値電圧 ${V_{th}}$ に加えて ${I_D}$ に依存したオーバードライブ電圧：  
${\Delta_{ov}=\sqrt{\frac{2I_D}{\beta}}}$   
をゲートに加えると説明でき、以下の式となる。  

$$ V_{GS}=V_{th}+\Delta_{ov} $$
$$ V_{DS} = \Delta_{ov} $$

チャネル長変調を含めると：

$$ I_D = I_{Dsat}(1 + \lambda V_{DS}) $$

トランスコンダクタンス

相互コンダクタンス：

$$ g_m = \frac{\partial I_D}{\partial V_{GS}} = \mu_n C_{ox} \frac{W}{L}(V_{GS}-V_{th}) $$

飽和領域では：

$$ g_m = \sqrt{2\mu_n C_{ox}\frac{W}{L} I_D} $$

ダイオード接続 MOSFET

ゲートとドレインを接続すると ${V_{GS} = V_{DS}}$ となり、

$$ I_D = \frac{1}{2}\mu_n C_{ox}\frac{W}{L}(V_{GS}-V_{th})^2 $$

等価抵抗 ${r_d = 1/g_m}$

[手書きメモ](assets/pdf/MOSFET_1.pdf)
