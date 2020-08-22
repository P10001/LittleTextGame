# LittleTextGame
简单的文字冒险游戏，游戏文件放在exe目录的data文件夹下<br>
游戏文件格式：<br>
<span style="text-indent:2em;">正文</span> <br>
<span style="color:green;">Page</span>@页名@{<br>
 &nbsp;游戏正文...<br>
 [条件]@<span style="color:green;">Page</span>@ 分支页名称@<br>
 [条件]#行为1,行为2,行为3#<br>
}<br>
<span style="color:green;">Page</span>@@分支页名称@{<br>
 分支页正文<br>
}<br>

其中，条件格式为\[(条件1)(条件2)(子条件1,子条件2)\]<br>
一个行为或一个分支只有在前面的条件满足时才会触发<br>
中括号为空，则后接的分支或行为语句为无条件执行<br>
中括号内的各条件之间是或关系，小括号内的条件是和关系<br>
行为的格式为 lhs op rhs<br>
其中lhs是已经定义的变量，在使用前需定义，op可以为=、+、-、*<br>
rhs为变量或字面量<br>
定义变量的方式为[标志]#变量名=初始值#<br>
标志可以为i和w，分别为整数和字符串，在后面加上+时变量为可查询变量，在游戏中可以使用"Q"查询<br>
变量名为外部命令和#[]以外的符号<br>
行为的另一种格式为 外部命令 rhs<br>
外部命令列表<br>
RET 返回到上一个有选项的页面<br>
OUT rhs 输出rhs，rhs是变量名时输出变量值，否则直接输出<br>
OUT_SP rhs 输出rhs个空格，rhs必须是数字或已定义的整数变量<br>
OUT_R rhs 输出rhs个\n，rhs要求同上<br>
SET_SC rhs 将两个文字的输出间隔时间设置为rhs毫秒，rhs要求同上<br>
SET_SL rhs 将两行文字的输出间隔时间设置为rhs毫秒，rhs要求同上<br>
RND_L rhs 将随机数范围的下限设定为rhs，rhs要求同上<br>
RND_H rhs 将随机数范围的上限设定为rhs，rhs要求同上<br>
RND rhs 使rhs等于（下限\~上限-1）中的一个随机值，若未设定上下限，默认值分别为0和10，即取值0~9<br>
