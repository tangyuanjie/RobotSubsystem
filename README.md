##一、项目名称
基于桌面冰球游戏的机器人实时控制子系统设计
 
##二、项目要求

 - **输入：**目标击球位置，到达该位置的时间，以及在该位置击球器的速度矢量。
 - **输出：**在每个控制周期给出X轴和Y轴的实时位置和速度指令。
 - **主要参数：**X轴和Y轴的最大行程、最大速度加速度限制。
 - **功能：**能够根据输入的运动目标指令，实时规划从当前位置达到目标击球位置的运动轨迹，以及到达击球位置后的减速停止轨迹，在每个控制周期输出X轴和Y轴的位置和速度设定值。

##三、项目成员

欧梓峰 盛玉庭 黄杰 张钊

![](http://images2015.cnblogs.com/blog/1069177/201612/1069177-20161229152520570-75695802.png)

##四、需求分析

###基本需求
 1. 在每周期内读入目标击球位置，到达位置的时间，以及在该位置击球器的速度矢量。
 2. 通过读入的参数计算加速度和匀速阶段的速度。
 3. 实现一个点从静止直线运动到另一个目标点然后减速到静止。
 4. 实现碰撞前轨迹规划和碰撞后的轨迹规划。
 5. 实时输出每个控制周期点的二维坐标和速度矢量。

###高级需求
 1. 设计起始点到目标点的路径规划。
 2. 根据规划的路径求两轴机械手的运动学反解得到每轴的角速度和角加速度。
 
### NABC需求分析
 - NEED
 1.在冰球游戏中，当用户感觉到累、实力不足，希望能有一个自动的系统帮助用户继续将冰球游戏进行下去或者希望一个高水平的系统帮助自己获得胜利，而这个系统便是机械手
 2.机械手能帮助用户解决没有对手的联系模式，即使一个人也可以享受冰球游戏的乐趣。
 - Approach
设计一个机械手实时控制子系统软件模块（RobotSubsyste），在知道击球点、击球速度矢量、到达击球时间下，设计一个软件模块使机械手能自动沿着规划的轨迹在一定的时间内到达击球位置使得击球成功。
 - Benefit
1.该子系统能实时显示冰球的位置、所控制击球器的位置，利于用户掌握冰球的系统的信息，有更好的游戏体验
2.该子系统实现击球的功能使得用户练习或者单独一人时有了更好的游戏体验
 - competitors
有些冰球游戏中，机械手与冰球的相对位置并不是一定要依靠软件编程来实现，可使用传感器使得机械手获得冰球的位置。

##五、功能分解

![](http://images2015.cnblogs.com/blog/1069581/201701/1069581-20170104101136831-2061734150.png)
