# NEU ipgw manager
![](https://img.shields.io/badge/NEU-ipgw--manager-blue.svg)


      <svg xmlns="http://www.w3.org/2000/svg" width="128" height="128" viewBox="0 0 128 128">
  <metadata><?xpacket begin="﻿" id="W5M0MpCehiHzreSzNTczkc9d"?>
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="Adobe XMP Core 5.6-c142 79.160924, 2017/07/13-01:06:39        ">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""/>
   </rdf:RDF>
</x:xmpmeta>                       
<?xpacket end="w"?></metadata>
<defs>
    <style>
      .cls-1 {
        fill: #156586;
      }

      .cls-1, .cls-2 {
        fill-rule: evenodd;
      }

      .cls-2 {
        fill: #f1ff0c;
      }

      .cls-3 {
        fill: #fff;
      }
    </style>
  </defs>
  <path id="形状_1" data-name="形状 1" class="cls-1" d="M36,52H10L0,62v4L10,76H68v8H18l26,26V92h8v26l10,10h4l10-10V60h8v50l26-26H92V76h26l10-10V62L118,52H60V44h50L84,18V36H76V10L66,0H62L52,10V68H44V18L18,44H36v8Z"/>
  <path id="椭圆_1" data-name="椭圆 1" class="cls-2" d="M100.5,99.2A14.4,14.4,0,1,1,86,113.6,14.45,14.45,0,0,1,100.5,99.2Zm1.45-5.76"/>
  <path id="形状_2" data-name="形状 2" class="cls-2" d="M104.85,106.4V60.32L100.5,56l-5.8,5.76,1.45,2.88L94.7,66.08v8.64l2.9,2.88v1.44l-2.9,2.88v1.44l1.45,1.44v1.44L94.7,87.68v1.44l1.45,1.44L94.7,92v4.32H93.25V106.4h11.6Z"/>
  <circle id="椭圆_2" data-name="椭圆 2" class="cls-3" cx="100.5" cy="120.5" r="3.5"/>
</svg>

东北大学新版ipgw网关管理程序。

由于校内网关切换到统一认证，原有的用户名+密码登录网关的方式彻底失效。新版本的ipgw管理程序使用python编写，直接可以支持跨平台使用。

通过对学校ipgw的API提取解析后得到的纯粹的客户端，拥有高度的灵活性和定制性。

**程序尚未编写安装和设置读取模块，直接运行main.py并保证所有依赖项都在同一个目录下即可运行。**
## 用法
```
ipgw | ipgw -i | ipgw --login <username>
```
尝试使用设置中保存的cookie在当前ip登录网关。

如果cookie过期或失效需要重新认证，则会自动根据设置中保存的账号密码登录SSO，重新获取cookie并更新设置。
```
ipgw -o | ipgw --logout <uid>
```
登出当前账号上登录的任何设备（如果指定了uid编号，则登出指定的设备）
```
ipgw -c | ipgw --current
```
列出当前账号登录的所有ip、使用流量、使用时长，并指出当前登录的ip是否有其他账号登录。
```
ipgw -s | ipgw --status
```
尝试使用设置中保存的校园网网络管理后台账号密码登录网络中心后台，返回已用时长、套餐总额、剩余流量等信息。
```
ipgw --config
```
返回配置文件绝对路径。
