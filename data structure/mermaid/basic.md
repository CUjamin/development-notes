graph  TB（top--botom 上下排列）

graph BT  (botom--top)

graph  LR（left--right 左右排列）

graph  RL (right--left)

-->    在流程图中显示——>

---    在流程图中显示——

# 基础模型
```mermaid
graph LR;
　　Portal-->|发布/更新配置|Apollo配置中心;
　　Apollo配置中心-->|实时推送|App;
　　App-->|实时查询|Apollo配置中心;
```

# 结构模型
```mermaid
graph TB
　　client-->|2 findConfigServices|LoadBalancer;
　　LoadBalancer-->|3 findService|metaServer;
　　metaServer-->Eureka;
　　client-->|4 access via ip:port/client load balance/error retry|ConfigService;
　　ConfigService-->|1 register/cancel|Eureka;
　　ConfigService-->|read/write|ConfigDB;
```

# 模块依赖图
```mermaid
graph LR;
　　client---core;
　　client---common;
　　core---common;
　　common---portal;
　　common---Biz;
　　Biz---ConfigService;
　　Biz---AdminService;
```


```mermaid
graph LR;
　　A-->|A指向B|B;
　　B---|B与C相连|C;
```

# 序列图
```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John:hello John
    loop healthcheck
        John-->>John:fight against
    end
    Note right of John:rational
    
    John->>Alice:great!
    John->>Bob:how about you
    Bob->>John:good!

```