# 快速上手
## StateManager快速上手
1.直接运行程序目录中的 SMCore.exe。  
2.从右下角托盘图标点右键->执行控制(或连接管理、报警列表)，查看实例列表、连接列表、报警列表的界面。  
3.打开Script目录的js/vbs等文件，修改其中脚本内容，然后在“执行控制”相应的行点击右键->复位，观察执行效果。  
4.更多功能，可加入官方QQ交流群学习：244671697  

## StateManager目录结构
bin 二进制文件，含三方插件等    
--debug    
----Log 用户写日志功能产生的日志，以实例为子目录，以及系统日志    
----Script 用户js/vbs脚本文件（可选）    
----HostDemo.exe 类库方式运行状态机的宿主示例程序（根据需要自行编写主程序）    
----globaljs 全局js脚本工具代码（可选）  
----HslCommunication.dll 一款非常好用的通讯连接类库（使用SMConnectionHsl.dll对接，详见SMConnectionHsl代码）  
----Interop.MSScriptControl.dll 脚本支持功能（必须附带）  
----Newtonsoft.Json.dll 程序配置json文件的解析工具 （必须附带）   
----Oracle.ManagedDataAccess.dll 数据库ORACLE连接工具（使用SMConnectionORACLE.dll时需附带）  
----project.json 状态机配置文件，内含所有配置
----SMAdmin.dll 状态机实例列表界面（可选）   
----SMAlarm.dll 报警插件  （可选）   
----SMAlarm.db  报警插件文件数据库（可选）   
----System.Data.SQLite.dll  报警插件SMAlarm.dll需要这个（可选）   
----SMConnection.dll  网络连接管理的插件，完成所有网络连接统一管理，自动重连（使用SMConnectionHsl、TCP.dll等时需附带）  
----SMConnectionMSSQL.dll  用于连接MSSQL数据库  
----SMConnectionORACLE.dll 用于连接ORACLE数据库
----SMConnectionHsl.dll 用于连接西门子三菱PLC等
----SMConnectionSocket.dll  用于连接TCP/UDP  
----SMCore.exe  状态机框架核心类库，如果不编写宿主程序的话也可以从这直接运行状态机，从右下角托盘可以打开功能界面 
HostDemo  宿主程序的示例代码
SMConnectionMSSQL  此文件夹为SMConnectionMSSQL源代码  
SMConnectionORACLE  此文件夹为SMConnectionORACLE源代码  
SMConnectionHsl  此文件夹为SMConnectionHsl源代码  
SMConnectionSocket  此文件夹为SMConnectionSocket源代码  
StateManager.sln  解决方案  




