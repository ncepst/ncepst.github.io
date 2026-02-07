基本式

電荷密度はゲート酸化膜容量によって誘起される

$$ I = q N v S $$

誘起電荷 

$$ qN = C_{ox}(V_{GS} - V_{th}) $$

電流密度：

$$ J = q N \mu_n E $$

チャネル電位分布 ${V(0)=0,　V(L)=V_{DS}}$

チャネル内の電荷分布

チャネル位置 ${x}$ における電荷密度：

$$ qN(x) = C_{ox}(V_{GS} - V_{th} - V(x)) $$

電流密度：

$$ J(x) = C_{ox}(V_{GS} - V_{th} - V(x)) \mu_n \frac{dV(x)}{dx} $$

ドレイン電流の導出

電流はチャネル全体で一定 ${I = W J(x)}$

積分すると：

$$ I = \mu_n C_{ox} \frac{W}{L} \left[(V_{GS}-V_{th})V_{DS} - \frac{1}{2}V_{DS}^2\right] $$

線形領域の電流式：

$$ I_D = \mu_n C_{ox} \frac{W}{L} \left[(V_{GS}-V_{th})V_{DS} - \frac{1}{2}V_{DS}^2\right] $$

飽和領域

ピンチオフ条件：

$$ V_{DSsat} = V_{GS} - V_{th} $$

飽和電流：

$$ I_{Dsat} = \frac{1}{2}\mu_n C_{ox}\frac{W}{L}(V_{GS}-V_{th})^2 $$

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
