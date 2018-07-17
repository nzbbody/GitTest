# eval-flkcdp

## 项目介绍
1. eval-flkcdp使用BenchmarkSQL测试性能
2. 这个工程是从原始的[cryptdb](https://github.com/CryptDB/cryptdb/)中的eval目录剪切过来的
3. 为了能够测试 flkcdp，代码做了一部分修改， 同时为了工程的简洁，把一部分用不到的文件放到了backup目录

## 环境配置
1. 安装 ant，apt-get install ant

## 编译构建
1. 进入BenchmarkSQL-2.3.3目录，执行ant
2. 可以修改BenchmarkSQL加载数据的规模，操作如下：
   * 在当前目录grep -i "100,000" ./ -Rn，找到对应的文件位置
   * 修改数据，然后重新执行ant

## 项目运行
进入BenchmarkSQL-2.3.3/run目录，在run目录包含4个子目录，如下：
1. load_enc_no测试加载数据的性能，对比flkcdp和mysql不加密的性能
   * test_load_flkcdp.sh  测试flkcdp的加载性能
   * test_load_mysql.sh   测试mysql的加载性能
   * report.sh            自动输出flkcdp和mysql的性能对照报告
2. load_enc测试加载数据的性能，对比flkdp在各种加密情况下的性能
   * test_load_enc_no.sh         测试flkcdp不加密的加载性能
   * test_load_enc_int_one.sh    测试flkcdp加密一个int字段的加载性能
   * test_load_enc_float_one.sh  测试flkcdp加密一个float字段的加载性能
   * test_load_enc_string_one.sh 测试flkcdp加密一个string字段的加载性能
   * test_load_enc_int.sh        测试flkcdp加密所有int字段的加载性能
   * test_load_enc_float.sh      测试flkcdp加密所有float字段的加载性能
   * test_load_enc_string.sh     测试flkcdp加密所有string字段的加载性能
3. tpmc_enc_no测试tpmc性能，比flkcdp和mysql不加密的性能
   * tpmc_enc_no_flkcdp.sh 测试不加密的情况下，flkcdp的tpmc指标
   * tpmc_enc_no_mysql.sh  测试不加密的情况下，mysql的tpmc指标 
4. tpmc_enc测试tpmc性能，对比flkdp在各种加密情况下的性能
   * tpmc_enc_no.sh         测试不加密的情况下，flkcdp的tpmc指标
   * tpmc_enc_int_one.sh    测试加密一个int字段的情况下，flkcdp的tpmc指标
   * tpmc_enc_float_one.sh  测试加密一个float字段的情况下，flkcdp的tpmc指标
   * tpmc_enc_string_one.sh 测试加密一个string字段的情况下，flkcdp的tpmc指标
   * tpmc_enc_int.sh        测试加密所有int字段的情况下，flkcdp的tpmc指标
   * tpmc_enc_float.sh      测试加密所有float字段的情况下，flkcdp的tpmc指标
   * tpmc_enc_string.sh     测试加密所有string字段的情况下，flkcdp的tpmc指标
