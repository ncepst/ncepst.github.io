■SPI
SCLK, MOSI, MISO, CSの4線の同期シリアル通信  

CSがH⇒Lで通信開始、CSがL⇒Hで通信の区切り(終了)  
プッシュプル出力(L, H, HighZ)、全二重通信  

■I2C
SCL, SDAの2線の同期シリアル通信  

スタート条件: SCLがHのときにSDAがH⇒L  
データ通信: SCLがLのときにSDAが切り替わって、SCLがHのときにSDAの値をREADする  
ストップ条件: SCLがHのときにSDAをL⇒H  
ACKはSDA＝L、NACKはSDA＝H  

START→アドレス(7bit)+R/W(1bit)→ACK→データ(8bit)→ACK→...→STOP  
オープンドレイン出力  

■UART
非同期シリアル通信  
スタートビット、ストップビット、ボーレート誤差をどこまで許容できるか
