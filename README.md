关于链式节点使用方法：

1. 需要先使用自定义订阅转换模版拉取机场节点，再手动修改YAML文件  
2. 加你的落地IP信息添加到代理列表  
   找到 proxies: 组  
   添加信息，例如  
   `  - {name: Cliproxy-新加坡, type: socks5, server: 111.11.11.11, port: 443, username: "xxxx", password: "xxxxxxb", udp: true, dialer-proxy: 链式-代理}`  
3. 找到莲式落地组，将代理名称添加到分组  
   `  - name: 链式-落地`  
   `    type: select`  
   `    proxies:`  
   `      - DIRECT`  
   `      - Cliproxy-新加坡`  
4. 保存，重起clash
5. 使用时，先在域名组选中链式落地，后在链式落地组中选择具体落地IP，最后在莲式代理组选择中间的机场代理
