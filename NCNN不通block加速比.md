### NCNN测速比,硬件平台为3299
#### 记录一下ncnn中param文件的特殊参数，0：输出通道 1：kernel 2:dilation 3:stride 4:pad 5:bias 6:weight_size 7:group 8:int8 9:activation_type 10:activation_params 其中weight_size的计算要尤其注意，如果是1x1卷积，则为输入通道x输出通道，如果是3x3卷积，则为3x3x输入通道x输出通道 若为dw卷积，则是3x3x输出通道
| block名称         |  size       |  fp32/ms   |   int8/ms   |    比例    |
| :----------------|------------ | :---------: | :---------: |:------:   | 
| residual block   |   320x240   |  513.43     |  199.25     |   0.611  |
|    |   160x120   |  106.53     |  50.53      |   0.525  |
|    |    80x60    |  26.97      |  17.95      |   0.334  |
|  |    40x30    |  7.59       |  7.83       |   -0.03  |
