---
title: Khái niệm phát triển ứng dụng
---

# Khái niệm phát triển ứng dụng

## Giới thiệu

Mục tiêu đầu tiên của bạn là hiểu về phân tích cảm xúc, để bạn có bối cảnh khi tiếp cận việc phát triển ứng dụng phân tích cảm xúc. Bạn sẽ làm quen với khái niệm phân tích cảm xúc là gì, các loại phân tích cảm xúc khác nhau, tầm quan trọng của phân tích cảm xúc, cách phân tích cảm xúc hoạt động và các trường hợp sử dụng phân tích cảm xúc khác nhau.

## Chuẩn bị

- Đọc qua tổng quan về "Xây dựng một ứng dụng phân tích cảm xúc"

## Đề mục

- [Sentiment Analysis Fundamentals](#sentiment-analysis-fundamentals)
- [Summary](#summary)
- [Further Reading](#further-reading)

## Cơ bản về Phân tích Cảm xúc (Sentiment Analysis)

### Phân tích Cảm xúc là gì?

Phân tích cảm xúc là quá trình xác định và trích xuất ý kiến trong văn bản và trích xuất các thuộc tính từ các biểu đạt thông qua việc sử dụng hệ thống tận dụng Xử lý Ngôn ngữ Tự nhiên. Ý kiến là một biểu đạt chủ quan mô tả cảm xúc, đánh giá và cảm nhận của mọi người về một chủ đề hoặc vấn đề. Phân loại chủ quan có thể xác định xem một câu hoặc biểu đạt có tính chủ quan hay khách quan. Phân loại tính chất có thể xác định cảm xúc từ một tập hợp văn bản (toàn bộ tài liệu, đoạn văn, câu đơn hoặc biểu đạt con) xem có tính tích cực, tiêu cực hay trung lập. Ý kiến có hai loại: ý kiến trực tiếp và ý kiến so sánh. Ý kiến trực tiếp đưa ra một biểu đạt chủ quan về một thực thể trực tiếp trong khi ý kiến so sánh diễn tả sự tương đồng hoặc khác biệt giữa hai hoặc nhiều thực thể bằng cách sử dụng hình thức so sánh hoặc siêu so sánh của tính từ hoặc trạng từ.

### Các loại Phân tích Cảm xúc khác nhau là gì?

Có nhiều loại hệ thống phân tích cảm xúc khác nhau, từ việc tập trung vào tính chất, phát hiện cảm xúc và tình cảm, đến xác định ý định. Các loại phân tích cảm xúc bao gồm phân tích cảm xúc chi tiết, phát hiện cảm xúc, phân tích cảm xúc dựa trên khía cạnh, phân tích ý định, phân tích cảm xúc đa ngôn ngữ. Phân tích cảm xúc chi tiết mở rộng phạm vi tính chất từ tích cực, trung lập hoặc tiêu cực thành rất tích cực, tích cực, trung lập, tiêu cực hoặc rất tiêu cực. Phát hiện cảm xúc thường tận dụng từ điển hoặc thuật toán học máy để liệt kê từ hoặc tập văn bản và phân tích cảm xúc mà chúng truyền đạt. Phân tích cảm xúc dựa trên khía cạnh đi sâu vào phân tích các khía cạnh hoặc đặc điểm cụ thể của một sản phẩm hoặc dịch vụ mà mọi người đề cập đến, bên cạnh mức độ tính chất. Phân tích ý định phát hiện những gì mọi người sẽ làm với một văn bản thay vì những gì mọi người nói về văn bản đó. Phân tích cảm xúc đa ngôn ngữ phát hiện ngôn ngữ trong văn bản một cách tự động thường sử dụng thuật toán học máy và thực hiện phân tích trên văn bản để thu thập cảm xúc.

### Tại sao Phân tích Cảm xúc quan trọng?

80% số liệu trên thế giới là không có cấu trúc, hầu hết đến từ dữ liệu văn bản, điều này khó khăn, tốn thời gian và tốn kém để phân tích, hiểu và sắp xếp. Phân tích cảm xúc là rất quan trọng để các công ty có thể hiểu được sự phong phú của dữ liệu văn bản không có cấu trúc này, bởi vì họ có thể tự động hóa quy trình kinh doanh, thu được thông tin hữu ích, tiết kiệm giờ đồng hồ trong việc xử lý dữ liệu thủ công và cuối cùng làm cho đội ngũ hiệu quả hơn. Phân tích cảm xúc cung cấp tính mở rộng, phân tích thời gian thực, tiêu chí nhất quán. Bạn có thể tưởng tượng công việc đáng sợ của việc sắp xếp hàng ngàn tweet, cuộc trò chuyện hỗ trợ khách hàng hoặc đánh giá của khách hàng? Có quá nhiều dữ liệu để xử lý thủ công, nhưng với sự trợ giúp từ hệ thống phân tích cảm xúc, mọi người có thể xử lý dữ liệu ở quy mô lớn một cách hiệu quả. Phân tích cảm xúc có thể được sử dụng để xác định các tình huống quan trọng trong thời gian thực và cho phép thực hiện hành động ngay lập tức. Các công ty sử dụng hệ thống phân tích cảm xúc tập trung có thể áp dụng tiêu chí nhất quán cho tất cả dữ liệu của họ, giảm thiểu lỗi và không nhất quán khi người ta đánh giá cảm xúc của văn bản. Thường thì khi thực hiện phân tích cảm xúc trên một đoạn văn bản, mọi người thường liên kết với kinh nghiệm cá nhân, suy nghĩ và niềm tin của mình.

### Hoạt động như thế nào?

Có nhiều phương pháp và thuật toán được sử dụng trong thực tế để phát triển hệ thống phân tích cảm xúc: Rule-Based (dựa trên quy tắc), Automatic (tự động) và Hybrid (kết hợp).

Hệ thống dựa trên quy tắc sử dụng một tập hợp các quy tắc được tạo thủ công để thực hiện phân tích cảm xúc. Những quy tắc này thường sử dụng nhiều thông tin đầu vào, kỹ thuật xử lý ngôn ngữ tự nhiên cổ điển và từ điển. Một ví dụ về cách thực hiện hệ thống dựa trên quy tắc là đầu tiên xác định một danh sách các từ có tính chất phân cực, tiếp theo đếm số lượng từ tích cực và tiêu cực từ đầu vào, cuối cùng kiểm tra xem số lần xuất hiện từ tích cực có lớn hơn số lần xuất hiện từ tiêu cực hay không. Nếu đúng, trả về cảm xúc tích cực, ngược lại trả về cảm xúc tiêu cực.

Hệ thống tự động sử dụng một Bộ phân loại Học máy, đưa văn bản làm đầu vào và trả về danh mục tương ứng: tích cực, tiêu cực hoặc trung lập (nếu phân tích tính chất được thực hiện). Bộ phân loại Học máy thường được thực hiện trong hai giai đoạn:

Giai đoạn đầu tiên liên quan đến huấn luyện mô hình để liên kết đầu vào (văn bản) với đầu ra tương ứng (nhãn hoặc thẻ), dựa trên các mẫu kiểm tra được sử dụng để huấn luyện. Quá trình này bao gồm đưa dữ liệu đầu vào qua một bộ trích xuất đặc trưng chuyển đổi đầu vào văn bản thành một vectơ đặc trưng. Các vectơ đặc trưng được đưa qua một hàng đợi và cặp cả vectơ đặc trưng và nhãn (cảm xúc tích cực, tiêu cực hoặc trung lập) được đưa vào thuật toán học máy để tạo ra mô hình.

<!-- Include picture on the training process -->

- Giai đoạn cuối cùng liên quan đến dự đoán điểm cảm xúc cho đầu vào ngẫu nhiên. Quá trình xử lý dữ liệu bao gồm việc đưa dữ liệu đầu vào thô qua bộ trích xuất đặc trưng để chuyển đổi thành một vectơ đặc trưng, sau đó đưa vào mô hình để tạo ra nhãn dự đoán, như tích cực, tiêu cực hoặc trung lập.

<!-- Include picture on the prediction process -->

Các thuật toán Học máy phổ biến có thể được sử dụng trong phân loại văn bản bao gồm Naive Bayes, Linear Regression, Support Vector Machines, Deep Learning và Gradient Boosted Trees (GBTs).

- **Gradient Boosted Trees (GBTs)**: huấn luyện một chuỗi cây quyết định để xây dựng mô hình phân loại. Nó sử dụng nhóm hiện tại của các vectơ đặc trưng để dự đoán tính chất phân loại (như tích cực, tiêu cực hoặc trung lập) của mỗi ví dụ huấn luyện và cuối cùng so sánh dự đoán với nhãn thực tế.

- **Deep Learning**: cố gắng mô phỏng cách não bộ con người hoạt động bằng cách sử dụng mạng nơ-ron nhân tạo để xử lý dữ liệu. Phân tích cảm xúc có thể được thực hiện để phân loại văn bản theo 2 cách, cách thứ nhất là sử dụng học có giám sát nếu có đủ dữ liệu huấn luyện, nếu không sử dụng học không giám sát sau đó kết hợp với một bộ phân loại có giám sát để huấn luyện mô hình mạng nơ-ron sâu. Mạng nơ-ron sâu được sử dụng để xây dựng các mô hình phân loại cảm xúc bao gồm mạng nơ-ron đệ quy, word2vec, paragraph vectors, mạng nơ-ron hồi quy, v.v.

- **Support Vector Machines**: là các mô hình phi xác suất biểu diễn các ví dụ văn bản dưới dạng các điểm trong không gian đa chiều. Các ví dụ văn bản này được ánh xạ vào các danh mục khác nhau, chẳng hạn như cảm xúc: vui vẻ, buồn bã, tức giận, v.v. Các danh mục này thuộc về các khu vực riêng biệt trong không gian đa chiều đó. Văn bản mới được ánh xạ vào cùng không gian và được dự đoán thuộc về một danh mục cụ thể.

- **Linear Regression**: là một thuật toán được sử dụng trong thống kê và học máy để dự đoán một giá trị (Y) dựa trên tập hợp các đặc trưng (X).

Naive Bayes: là một tập hợp các thuật toán học máy có giám sát sử dụng định lý Bayes để dự đoán danh mục của văn bản.

### Các ứng dụng của Phân tích Cảm xúc

- Giám sát mạng xã hội
- Giám sát thương hiệu
- Lắng nghe ý kiến khách hàng (Voice of Customer - VoC)
- Dịch vụ khách hàng
- Phân tích nhân sự và ý kiến nhân viên (Voice of Employee)
- Phân tích sản phẩm
- Nghiên cứu và phân tích thị trường

## Tổng kết

Xin chúc mừng! Bây giờ bạn đã hiểu cơ bản về phân tích cảm xúc. Bạn đã sẵn sàng thiết lập môi trường phát triển cho ứng dụng.

## Tìm hiểu thêm

- Để tìm hiểu sâu về Phân tích Cảm xúc, tham khảo bài viết của MonkeyLearn [Phân tích cảm xúc - Hầu hết các điều bạn cần biết](https://monkeylearn.com/sentiment-analysis/)
- [Sử dụng deep learning để phân tích cảm xúc như thế nào?](https://www.quora.com/How-is-deep-learning-used-in-sentiment-analysis)
