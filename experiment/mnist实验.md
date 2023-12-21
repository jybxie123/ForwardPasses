# 实验记录

因为一个cuda跑了一天。测试如下：

总结一下基本规则：
torch,cudatoolkit,cuda driver三个是互相需要版本匹配的。
cuda driver本机一般不易更改，11.0以上可以用docker虚拟化；
cuda toolkit可以低于driver支持的版本，但是不一定保证兼容；
torch需要和toolkit兼容。


实验版本：

torch1.3.1，cuda 10.1, cuda driver12.0；结果：卡住

torch1.3.1，cuda12.0， cuda driver 12.0；结果：torch无法输出cuda版本，太老了识别不了

torch版本更高，python版本太老，不成功

师兄一遍搞定：所有依赖全部最新。

总结最好的解决方案：

全部依赖的版本要统一，既然driver的版本为12.0，那全部与它对齐，可兼容性最好。
