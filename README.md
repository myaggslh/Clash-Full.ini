关于链式节点使用方法：  

1、需要先使用自定义订阅转换模版拉取机场节点，再手动修改YAML文件  

2、加你的落地IP信息添加到代理列表  
找到 proxies: 组  
添加一行信息，例如  
`proxies:`  
`  - {name: Cliproxy-新加坡, type: socks5, server: 111.11.11.11, port: 443, username: "xxxx", password: "xxxxxxb", udp: true, dialer-proxy: 所有-手动}`

3、将落地IP信息添加到分组  
`  - name: 落地-手动`  
`    type: select`  
`    proxies:`  
`      - DIRECT`  
`      - Cliproxy-新加坡`  

4、保存，重起clash
