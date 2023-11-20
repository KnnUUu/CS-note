### What is LOAD BALANCING?
当需要处理大量请求时，一台服务器不足以应对，所以需要设置多台服务器。LOAD BALANCING用于解决客户端应该向哪台服务器发送请求的问题，使得各台服务器的负载均衡  
当请求增加时，需要增加服务器来应对。移动服务器数据时，应该尽可能保持原有状态，使得原有的缓存可以继续使用，所以需要使用constant hashing  
假设本来有4台服务器，需要增设到5台    
⭕：S1 S2 S3 S4各自减少5%，合并起来给新服务器S5（5+5+5+5+5）  
❌：S1减少5%合并到S2，S2减少10%合并到S3，S3减少15%合并到S4，S4减少20%构成S5（5+5+10+10+15+15+20+20）  

### Horizontal vs. Vertical Scaling
应对更多请求的方法，也就是scalability（可扩展性）  
1. 买台更大的电脑（Vertical Scaling）   
2. 买更多电脑（Horizontal Scaling）

trade-off
| |Vertical|Horizontal|
|:-------------:|:-------------:|:-------------:|
|Load Balancing|need|not need|
|lots of machine|resilient⭐|single point of failure|
|IO cost|network calls|inter process communication⭐|
|data consistency|inconsist|consist⭐| 
|scale well as users increse|no⭐|yes|

Real world development:combine both methods benefits⭐　