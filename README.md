

## Wabei 命令行挖矿指南

#### 工具下载说明

> |工具包|系统版本|下载地址|
> |-|-|-|
> |geth-darwin-10.6-amd64|Mac|[下载地址](https://github.com/wabei/miner/blob/master/geth-darwin-10.6-amd64)|
> |geth-linux-amd64|linux|[下载地址](https://github.com/wabei/miner/raw/master/geth-linux-amd64/wabei-geth)|
> |geth-windows-4.0-amd64.exe|winodws|[下载地址](https://github.com/wabei/miner/raw/master/geth-windows-4.0-amd64/wabei-geth.exe)|
> |geth-linux-arm64|linux|[下载地址](https://github.com/wabei/miner/blob/master/geth-linux-arm64)|
> |下载以上对应版本并修改文件名为：geth(后缀不变）|
#### linux 系统终端命令行挖矿指南

  1. 准备工作
	
  - linux 下载 [geth-linux-amd64](https://github.com/wabei/miner/geth-linux-amd64) 到本地目录

````
  
  # 打开终端输入，复制geth 到bin目录
    mv geth /usr/local/bin  

  # 授给geth授权
    chmod +x /usr/local/bin/geth
````
  
  2. 启动挖矿
  
  - 本地方式直接启动挖矿
  ````
    #打开终端，sudo -s 回车输入密码，进入root目录，输入
      geth console  //回车，进入了控制台

    # 控制台下输入：
      personal.newAccount("你的密码") //回车生成你的矿工账户。

    # 启动挖矿：
    exit 回车，退出控制台后，输入 geth --mine 启动挖矿，此时关闭窗口也可以，geth将进入后台运行挖矿
````
  
````
  #多机一个账户（root目录下pkill geth 然后：
  chmod +x start.sh  //修改start.sh文件中的账户为你的统一账户
  ./start.sh  //启动挖矿，关闭窗口不影响运行
````

#### Window 系统CMD命令行挖矿指南
 
 启动挖矿
 
````
  # 下载
    下载对应的操作系统版本，到D:/wabei目录

  # 启动控制台
    win+R 启动cmd 窗口

  # 进入D盘下的wabei目录
    D:        //在CMD输入D：回车进入D盘
    cd wabei  //进入wabei目录

  # 进入geth console控制台
    geth console 

  # 生成挖矿账户,注意保存账户地址，密码和对应的keystore
    personal.newAccount("你的密码")

  # 启动挖矿
    miner.start()    //也可以退出，使用geth --mine启动后台挖矿
````
  
#### Mac 系统挖矿指南
#### 其他系统，理论上支持，但不建议
#### 常用命令：
     # geth console与geth attach都是交互式控制台，只能选用一个,于控制台下执行下述命令：
     # 生成账户：personal.newAccount("1345666")  替换“”中的密码为自己的
     # 启动挖矿：miner.start()  //适用于控制台下启动挖矿，最好关闭控制台，用geth --mine启动后台挖矿。
     # 查挖矿账户余额：eth.getBalance(eth.coinbase)
     # 查询特定账户余额：eth.getBalance("0x60c8abe58c9dbc52a4ee9f......“) 替换“”中的账户为要查询的， 
     # 节点连接查询：admin.peers 
     # 命令行转账：
     ##personal.unlockAccout("账户“）
     ##eth.sendTransaction({from: '0x544.......', to: '0x02df.......', value: 100000000}) 
#### 在线钱包配套挖矿使用(适用于挖矿中的电脑）
     #wallet.bitwa.org //打开这个网站
     #pkill geth  //关闭现有挖矿进程：
     #geth --rpc --ws --wsorigins "wallet.bitwa.org" --mine //终端执行这条命令（替代geth console)、块高，同步完成后可转账操作\自动挖矿。
     #geth --rpc --ws --wsorigins "wallet.bitwa.org" --mine --unlock <your account> //这个命令比上一条增加了解锁账户，主要是方便转账。

