# CodeCraft-2023
2023年华为软件挑战赛粤港澳赛区51名,得分3000037(图一64.7万,图二77.9万,图三88.7万,图四68.4万)

主要模块:数据预处理模块,运动模块,调度模块
代码的主要思路是先对输入的数据进行处理,转化为更容易被代码处理的形式,比如把原材料格状态值转化为一个长度为8的数组.然后查看每个机器人可以去什么工作台买一个物品,并且可以去什么工作台卖
这个物品.我们设计了一种优先级计算方式,从众多选择中选择优先级最高的路径.然后调用运动模块,控制机器人走找到的优先级最高路径,完成买卖.

数据预处理模块:主要由函数bool input_every_frame(int frame_id, int &money, int k, vector<worktable> &worktable_array, vector<robot> &robot_array, vector<worktable> &worktable_array7)构成
函数的作用是接收每一帧的输入数据,并转化成更容易处理的形式

运动模块:主要由控制运动的函数bool robot_to_destination(robot &robot1, worktable &worktable1, vector<robot> &robot_array,vector<worktable> 
&worktable_array, int &frameID, vector<worktable> &worktable_array7)和判断碰撞情况的函数int coordinateTransform(robot robot1, robot robot2, int frameID)组成.

调度模块:主要由函数计算路径优先级最高的函数void findMaxPriority(vector<int> &worktableIndexBuyArray, vector<int> &worktableIndexSellArray,vector<worktable> &worktable_array, vector<robot> &robot_array,
  int &robotId, double &minDistance, int &minWorktableIndex,
                int &minWorktableSellIndex, vector<productPriority> &productPriorityArray, int &itemId,
                vector<worktable> &worktable_array7, int &frameID)构成
