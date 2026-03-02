# Table of contents

- [Giới thiệu](README.md)

## Chương 1: Bức tranh toàn cảnh (The Big Picture)

- [1.1. Vòng đời dữ liệu (Data Lifecycle)](chapters/01-big-picture/data-lifecycle.md)
- [1.2. Phân biệt OLTP vs OLAP](chapters/01-big-picture/oltp-vs-olap.md)
- [1.3. Sự tiến hóa: Data Warehouse tới Lakehouse](chapters/01-big-picture/evolution-to-lakehouse.md)

## Chương 2: Mô hình hóa Dữ liệu (Data Modeling)

- [2.1. Relational Modeling (Chuẩn hóa RDBMS)](chapters/02-data-modeling/relational-modeling.md)
- [2.2. Dimensional Modeling (Star/Snowflake Schema & Hive)](chapters/02-data-modeling/dimensional-modeling.md)
- [2.3. Data Vault Modeling](chapters/02-data-modeling/data-vault.md)
- [2.4. Thiết kế Schema phân tán (Partitioning & Clustering)](chapters/02-data-modeling/distributed-schema.md)

## Chương 3: Thu thập & Tích hợp Dữ liệu (Data Ingestion)

- [3.1. Message Brokers & Event Streaming (Apache Kafka)](chapters/03-ingestion/event-streaming-kafka.md)
- [3.2. Change Data Capture - CDC (Debezium)](chapters/03-ingestion/cdc-debezium.md)
- [3.3. Semantics trong Message Delivery (Exactly-once)](chapters/03-ingestion/delivery-semantics.md)

## Chương 4: Hệ thống Lưu trữ & Định dạng Dữ liệu (Storage & Formats)

- [4.1. File Formats & Metadata (Parquet, ORC, Avro)](chapters/04-storage-formats/file-formats.md)
- [4.2. Table Formats & Lakehouse (Apache Hudi, Iceberg)](chapters/04-storage-formats/table-formats-hudi.md)
- [4.3. Object Storage vs File System (MinIO, HDFS, S3)](chapters/04-storage-formats/object-storage.md)
- [4.4. Cơ sở dữ liệu Vector (Qdrant)](chapters/04-storage-formats/vector-databases-qdrant.md)

## Chương 5: Động cơ Xử lý & Phân phối (Compute Engines)

- [5.1. Xử lý Lô & Hợp nhất (Apache Spark)](chapters/05-compute-engines/batch-processing-spark.md)
- [5.2. Xử lý Luồng Trạng thái (Apache Flink)](chapters/05-compute-engines/stream-processing-flink.md)
- [5.3. Kiến trúc MPP & Real-time OLAP (StarRocks)](chapters/05-compute-engines/mpp-starrocks.md)
- [5.4. Federated Queries & Data Virtualization (Trino)](chapters/05-compute-engines/federated-queries-trino.md)

## Chương 6: Điều phối & Quản lý Luồng (Orchestration)

- [6.1. Directed Acyclic Graph - DAG (Apache Airflow)](chapters/06-orchestration/dag-airflow.md)
- [6.2. Event-driven Orchestration](chapters/06-orchestration/event-driven.md)

## Chương 7: Chất lượng, Quản trị & Bảo mật (Governance & Security)

- [7.1. Data Quality & Catalog (Lineage)](chapters/07-governance-security/data-quality-catalog.md)
- [7.2. Bảo mật, Xác thực & Phân quyền (Keycloak, OpenFGA, OPA)](chapters/07-governance-security/auth-security.md)

## Chương 8: Cơ sở Hạ tầng & DataOps (Infrastructure)

- [8.1. Containerization (Docker)](chapters/08-infrastructure/docker.md)
- [8.2. Container Orchestration (Kubernetes)](chapters/08-infrastructure/kubernetes.md)

## Chương 9: Kiến trúc Dữ liệu & Thiết kế Hệ thống (Architecture)

- [9.1. Đánh giá Trade-off trong Phân tán (CAP/PACELC)](chapters/09-architecture-design/distributed-tradeoffs.md)
- [9.2. Lambda vs Kappa Architecture](chapters/09-architecture-design/lambda-kappa.md)
- [9.3. Case Study: Hệ thống CDC Thời gian thực](chapters/09-architecture-design/case-study-realtime-cdc.md)
- [9.4. Case Study: Phân phối & Điều phối Dữ liệu (Backend Java/Spring Boot & ReactJS Frontend với Kong Gateway)](chapters/09-architecture-design/case-study-data-dispatching.md)
