# questdb

QuestDB 是一款高性能、开源的时间序列数据库。

## 项目链接

- GitHub: <https://github.com/questdb/questdb>
- 项目主页: <https://questdb.com>

## 项目介绍
QuestDB是一款开源低延迟时序数据库，支持高吞吐数据摄入、实时数据毫秒级计算与长期历史数据可查询。它采用统一SQL引擎覆盖数据摄入、流处理与分层存储，核心技术路径使用零GC Java，结合C++与Rust优化关键路径，数据存储采用内存映射、时间分区列存结构，支持SIMD与JIT编译过滤，无第三方数据路径依赖。

## 主要特性
1.  高性能：单实例峰值摄入可达1900万行/秒，Arrow流式查询速度达2.2亿行/秒
2.  开放存储：支持原生列存分区、并行预写日志，可通过`ALTER TABLE`转换为Apache Parquet格式，也可直接创建Parquet表；企业版可自动将冷分区分层存储到对象存储，兼容Apache Iceberg、Apache Arrow生态
3.  多部署方式：支持Docker、Homebrew快速启动，内置Web控制台与SQL接口
4.  无额外数据路径依赖，底层优化充分利用多核算力
