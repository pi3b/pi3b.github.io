# 常用组件的使用
StateManager状态机支持的组件可以是实现了IState接口的C#类，也可以是实现了3个接口函数的脚本。本演示中的脚本自身也是个组件。

如果要使用第三方功能，只需要编写实现接口的中间件组件即可。

C#组件要求实现：
```c#
    public interface IState
    {
        /// <summary>
        /// 所有对象创建完成后，按配置文件顺序初始化每个对象
        /// </summary>
        /// <param name="so">实例对象</param>
        void StateInit(SObject so);

        /// <summary>
        /// 状态处理函数，执行的条件为该实例为自动模式、且时间到了
        /// </summary>
        /// <param name="so"></param>
        void StateHandle(ref SObject so);

        /// <summary>
        /// 状态机停止时，按配置文件顺序执行每个对象，可编写一些网络连接等资源释放的代码
        /// </summary>
        /// <param name="so"></param>
        void StateFInit(SObject so);

        /// <summary>
        /// 实现此属性后，可以在so.使用，用于调出界面等可视化控制
        /// </summary>
        object Form { get; }//用object，这样用户不需要引用System.Windows.Forms;
    }
```

脚本组件要求实现(这里以js脚本为例)（注释同上）：
```js
function StateHandle(so){
}

function StateInit(so)
{
}

function StateFinit(so)
{
}
```


目前已开发好的常用组件包括： 
1. 连接管理组件（其中所有的连接都是一个个连接类型组件的实例，针对这种连接类型做的统一管理的组件）

![](demo-components-using_files/1.jpg)

2. 执行控制组件（统一管理所有实例的组件，显示执行过程，也可以控制所有实例的手自动切换、重置脚本、重载C#类库等）

![](demo-components-using_files/2.jpg)

3. 报警组件（收集报警信息、报警弹窗等功能）

![](demo-components-using_files/3.jpg)
![](demo-components-using_files/4.jpg)

4. 连接PLC的组件（使用了第三方组件）

5. 连接sqlserver/oracle数据库的组件

6. 连接Socket的组件。

7. HttpApi组件（实现简单的Http客户端和服务端功能）


其他组件陆续开发中。。。也欢迎大家共同参与开发！（详加左侧QQ群）
