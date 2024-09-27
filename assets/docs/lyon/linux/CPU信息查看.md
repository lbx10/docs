# 查看 CPU #

1. 查看物理 CPU 个数
  `cat /proc/cpuinfo |grep "physical id"|sort |uniq|wc -l`
2. 查看每个 CPU 具有几个核
  `cat /proc/cpuinfo |grep "cores"|uniq`
3. 查看逻辑 CPU 个数
`cat /proc/cpuinfo |grep "processor"|wc -l`
4. 查看 CPU 主频
`cat /proc/cpuinfo |grep MHz|uniq`

linux 下，CPU 硬件信息存放在/proc/cpuinfo 这个文件中。一个物理 CPU 可以有多个核（core），加上超线程技术（HT），可以逻辑上有多个 CPU。 不开启超线程情况下：逻辑 CPU 个数=物理 CPU 个数 x 核数。 开启超线程情况下：逻辑 CPU 个数=物理 CPU 个数 x 核数 x2。 注： linux 下使用 top 命令查看的 CPU 是逻辑 CPU 个数。
