L型マッチング回路の設計手順  

信号源抵抗 $$R_S$$  
負荷抵抗 $$R_L$$  
$$R_{high}=max(R_S,R_L)$$  
$$R_{low}=min(R_S,R_L)$$  

$$Q=\sqrt{\frac{R_{low}}{R_{high}} -1}$$  

①RL > Rsで LPF型  
　直列にインダクタ $${X_{S}=QR_S}$$ 、負荷と並列にキャパシタ $${X_{P}=-\frac{R_L}{Q}}$$    
②RL > Rsで HPF型  
　直列にキャパシタ $${X_{S}=-QR_S}$$ 、負荷と並列にインダクタ $${X_{P}=+\frac{R_L}{Q}}$$    
③RL < Rsで LPF型  
　源側と並列にキャパシタ $${X_{P}=-\frac{R_S}{Q}}$$  、負荷と直列にインダクタ $${X_{S}=+QR_L}$$     
④RL < Rsで HPF型  
　源側と並列にインダクタ $${X_{P}=+\frac{R_S}{Q}}$$  、負荷と直列にキャパシタ $${X_{S}=-QR_L}$$   
