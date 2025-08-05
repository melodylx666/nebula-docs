# 使用限制

本文描述 Exchange {{exchange.release}} 的一些使用限制。

## 使用环境

Exchange 3.x 支持以下操作系统：

- CentOS 7
- macOS

## 软件依赖

为保证 Exchange 正常工作，请确认机器上已经安装如下软件：

- Java 1.8 版本

- Scala 2.10.7、2.11.12 或 2.12.10 版本

- Apache Spark。使用 Exchange 从不同数据源导出数据对 Spark 版本的要求如下：
  
  !!! note

        使用 Exchange 时，需根据 Spark 版本选择相应的 JAR 文件。例如，当 Spark 版本为 2.4 时，选择 nebula-exchange_spark_2.4-{{exchange.release}}.jar。关于各版本 Spark 对应的 JAR 文件，请参见 [版本兼容性矩阵](https://github.com/vesoft-inc/nebula-exchange?tab=readme-ov-file#version-compatibility-matrix)。

  | 数据源 | Spark 2.2 | Spark 2.4 | Spark 3 |
  | - | - | - | - |
  | CSV 文件 | 支持 | 支持 | 支持 |
  | JSON 文件 | 支持 | 支持 | 支持 |
  | ORC 文件 | 支持 | 支持 | 支持 |
  | Parquet 文件 | 支持 | 支持 | 支持 |
  | HBase | 支持 | 支持 | 支持 |
  | MySQL | 支持 | 支持 | 支持 |
  | PostgreSQL | 支持 | 支持 | 支持 |
  | Oracle | 支持 | 支持 | 支持 |
  | ClickHouse | 支持 | 支持 | 支持 |
  | Neo4j | 不支持 | 支持 | 不支持 |
  | Hive | 支持 | 支持 | 支持 |
  | MaxCompute | 不支持 | 支持 | 不支持 |
  | Pulsar | 不支持 | 支持 | 未测试 |
  | Kafka | 不支持 | 支持 | 未测试 |
  | {{nebula.name}} | 不支持 | 支持 | 不支持 |

在以下使用场景，还需要部署 Hadoop Distributed File System (HDFS)：

- 迁移 HDFS 的数据
- 生成 SST 文件
