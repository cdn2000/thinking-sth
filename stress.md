# Stress 经验
* 最稳定可靠的是ab.
* 看好的是pewpew,因为功能强大，但压出来结果不理想，还有待改进。
* wrk 性能与ab类似，支持多线程，支持lua脚本的功能很吸引人，但采用脚本后会造成性能下降。
* TechEmpower中用python写的toolset.
* TechEmpowerk中对测试服务优设置如下：
###### 
    sudo sysctl -w net.ipv4.tcp_max_syn_backlog=65535
    sudo sysctl -w net.core.somaxconn=65535
    sudo -s ulimit -n 65535
    sudo sysctl net.ipv4.tcp_tw_reuse=1
    sudo sysctl net.ipv4.tcp_tw_recycle=1
    sudo sysctl -w kernel.shmmax=2147483648
    sudo sysctl -w kernel.shmall=2097152
  
* 最麻烦是Websocket性能测试，目前没发现好的工具。
