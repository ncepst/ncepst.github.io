トランスコンダクタンスはドレイン電流から

$$ g_m=\sqrt{2\beta I_D} $$

差動増幅回路はTail電流を用いて

$$ g_{md}=\sqrt{\beta I_{SS}} $$

ダイオードの電圧

$$ V_d=\frac{k_BT}{e}ln{\frac{I}{I_S}} $$

バンドギャップリファレンス（定電圧回路）

$$ V_{out}= V_{d3} + \Delta V_d \frac{R_2}{R_1} $$

$$ V_{out}= V_{d3} + \frac{k_BT}{e}ln{K} \cdot \frac{R_2}{R_1} $$

バンドギャップリファレンス（定電流回路）

$$ I_{out}= \frac{V_{d3}}{R_2} +  \frac{\Delta V_d}{R_1} $$

MOSの飽和条件

$$ V_{gs}-V_{th} <= V_{DS} $$

設計法：バイアス電流あたりトランスコンダクタンス

$$ \frac{g_m}{I_D} $$

を指標にする。
