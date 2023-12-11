---
title: Building a Sentiment Analysis Application
author: sandbox-team
tutorial-id: 770
experience: Advanced
persona: Data Engineer, Data Scientist
source: Hortonworks
use case: Data Discovery
technology: Apache Ambari, Apache NiFi, Apache Kafka, HDFS, Apache Hive, Apache HBase, Apache Spark, Apache Zeppelin
release: hdp-3.0.1, hdf-3.2.0
environment: Sandbox
product: CDA
series: CDA > Data Engineers & Scientists > Data Science Applications
---

# Xây dựng một Ứng dụng Phân tích Tâm trạng

## Giới thiệu

Cho dự án này, bạn sẽ đóng vai trò là một nhà phát triển ứng dụng Big Data, tận dụng kỹ năng của mình như một Kỹ sư Dữ liệu và Nhà khoa học Dữ liệu bằng cách sử dụng nhiều Công nghệ Big Data do Hortonworks Data Flow (HDF) và Hortonworks Data Platform (HDP) cung cấp để xây dựng một Ứng dụng Phân tích Tâm trạng Thời gian thực. Đối với ứng dụng này, bạn sẽ học cách thu thập dữ liệu tweet từ API Decahose của Twitter và gửi các tweet đó vào Chủ đề Kafka "tweets" bằng cách sử dụng NiFi. Tiếp theo, bạn sẽ học cách xây dựng Mô hình Học máy Spark để phân loại dữ liệu là vui vẻ hay buồn và xuất mô hình ra HDFS. Tuy nhiên, trước khi xây dựng mô hình, Spark yêu cầu dữ liệu xây dựng và huấn luyện mô hình phải ở dạng mảng đặc trưng, vì vậy bạn sẽ phải làm sạch dữ liệu bằng SparkSQL. Sau khi xây dựng xong mô hình, bạn sẽ sử dụng Spark Structured Streaming để tải mô hình từ HDFS, kéo các tweet từ chủ đề Kafka "tweets", thêm điểm tâm trạng vào tweet, sau đó truyền dữ liệu vào chủ đề Kafka "tweetsSentiment". Trước đó, sau khi hoàn thành quy trình NiFi, bạn sẽ xây dựng một quy trình NiFi khác để nhập dữ liệu từ chủ đề Kafka "tweetsSentiment" và lưu dữ liệu vào HBase. Với sự tích hợp của Hive và HBase, bạn sẽ thực hiện các truy vấn để hiển thị rằng dữ liệu đã được lưu trữ thành công và cũng hiển thị điểm tâm trạng cho các tweet.

### Các Công nghệ Big Data được sử dụng để phát triển Ứng dụng:

- [Twitter API](https://dev.twitter.com/)
- [HDF Sandbox](https://hortonworks.com/products/data-platforms/hdf/)
    - [Apache Ambari](https://ambari.apache.org/)
    - [Apache NiFi](https://nifi.apache.org/)
    - [Apache Kafka](http://kafka.apache.org/)
- [HDP Sandbox](https://hortonworks.com/products/data-platforms/hdp/)
    - [Apache Ambari](https://ambari.apache.org/)
    - [Apache Hadoop - HDFS](https://hadoop.apache.org/docs/r3.1.1/)
    - [Apache HBase](https://hbase.apache.org/)
    - [Apache Spark](https://spark.apache.org/)
    - [Apache Kafka](http://kafka.apache.org/)
    - [Apache Zeppelin](https://zeppelin.apache.org/)

### Mục tiêu

- Học cách tạo một Ứng dụng Twitter bằng cách sử dụng Cổng thông tin phát triển của Twitter để lấy Các khóa và Mã thông báo để kết nối với các API của Twitter.
- Học cách tạo một Ứng dụng Luồng dữ liệu NiFi tích hợp API Decahose của Twitter để nhập dữ liệu tweet, thực hiện một số tiền xử lý và lưu dữ liệu vào Chủ đề Kafka "tweets".
- Học cách tạo một Ứng dụng Luồng dữ liệu NiFi để nhập dữ liệu từ Chủ đề Kafka "tweetsSentiment" và truyền dữ liệu tweet tâm trạng vào HBase.
- Học cách xây dựng một Ứng dụng SparkSQL để làm sạch dữ liệu và đưa nó vào định dạng phù hợp để xây dựng mô hình phân loại tâm trạng.
- Học cách xây dựng một Ứng dụng SparkML để huấn luyện và xác nhận mô hình phân loại tâm trạng bằng cách sử dụng Gradient Boosting.
- Học cách xây dựng một Ứng dụng Spark Structured Streaming để truyền dữ liệu tweet tâm trạng từ chủ đề Kafka "tweets" trên HDP đến chủ đề Kafka "tweetsSentiment" trên HDF và đính kèm điểm tâm trạng cho mỗi tweet dựa trên kết quả của mô hình phân loại.
- Học cách trực quan hóa điểm tâm trạng của tweet bằng cách sử dụng trình thông dịch Hive của Zeppelin để ánh xạ vào bảng HBase.

### Chuẩn bị

- Tải về và triển khai [Hortonworks Data Platform (HDP)](https://www.cloudera.com/downloads/hortonworks-sandbox/hdp.html?utm_source=mktg-tutorial) Sandbox
- Đọc qua [Learning the Ropes of the HDP Sandbox](https://hortonworks.com/tutorial/learning-the-ropes-of-the-hortonworks-sandbox/) để thiết lập ánh xạ tên máy chủ thành địa chỉ IP.
- Nếu bạn không có 32GB RAM riêng cho HDP Sandbox, vui lòng tham khảo [Deploying Hortonworks Sandbox on Microsoft Azure](https://hortonworks.com/tutorial/sandbox-deployment-and-install-guide/section/4/)
- Kích hoạt Kiến trúc Dữ liệu Kết nối:
  - [Enable CDA for VirtualBox](https://hortonworks.com/tutorial/sandbox-deployment-and-install-guide/section/1/#enable-connected-data-architecture-cda---advanced-topic)
  - [Enable CDA for VMware](https://hortonworks.com/tutorial/sandbox-deployment-and-install-guide/section/2/#enable-connected-data-architecture-cda---advanced-topic)
  - [Enable CDA for Docker](https://hortonworks.com/tutorial/sandbox-deployment-and-install-guide/section/3/#enable-connected-data-architecture-cda---advanced-topic)

## Đề mục

Danh sách các module hướng dẫn bao gồm:

1\. **[Application Development Concepts](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/1/)** 
Bạn sẽ được giới thiệu về các khái niệm cơ bản về cảm xúc: phân tích cảm xúc, cách thực hiện phân tích dữ liệu và các trường hợp sử dụng khác nhau.

2\. **[Setting up the Development Environment](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/2/)** 
Bạn sẽ tạo một ứng dụng Twitter trong Developer Portal của Twitter để truy cập vào các KEY và TOKEN. Sau đó, bạn sẽ viết mã shell và thực hiện các cuộc gọi API REST của Ambari để thiết lập môi trường phát triển.

3\. **[Acquiring Twitter Data](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/3/)** 
Bạn sẽ xây dựng một luồng dữ liệu NiFi để nhập dữ liệu từ Twitter, tiền xử lý nó và lưu trữ vào Kafka Topic "tweets". Luồng dữ liệu NiFi thứ hai mà bạn sẽ xây dựng, nhập dữ liệu tweet cảm xúc đã được làm giàu từ Kafka topic "tweetsSentiment" và truyền nội dung của flowfile vào HBase.

4\. **[Cleaning the Raw Twitter Data](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/4/)** 
Bạn sẽ tạo một notebook Zeppelin và sử dụng Zeppelin's Spark Interpreter để làm sạch dữ liệu Twitter thô để chuẩn bị tạo mô hình phân loại cảm xúc.

5\. **[Building a Sentiment Classification Model](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/5/)** 
Bạn sẽ tạo một notebook Zeppelin và sử dụng Zeppelin's Spark Interpreter để xây dựng một mô hình phân loại cảm xúc nhận dạng các tweet là Vui vẻ (Happy) hoặc Buồn (Sad) và xuất mô hình vào HDFS.

6\. **[Deploying a Sentiment Classification Model](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/6/)** 
Bạn sẽ tạo một dự án Scala IntelliJ trong đó bạn phát triển một ứng dụng Spark Structured Streaming nhận dữ liệu từ Kafka topic "tweets" trên HDP, xử lý dữ liệu JSON của tweet bằng cách thêm cảm xúc và truyền dữ liệu vào Kafka topic "tweetsSentiment" trên HDF.

7\. **[Visualizing Sentiment Scores](https://hortonworks.com/tutorial/building-a-sentiment-analysis-application/section/7/)**
Bạn sẽ sử dụng Zeppelin's JDBC Hive Interpreter để thực hiện các truy vấn SQL đối với bảng noSQL HBase "tweets_sentiment" để có cái nhìn trực quan về điểm cảm xúc của các tweet.
