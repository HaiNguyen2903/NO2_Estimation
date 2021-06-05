# Ước lượng mật độ NO2 hàng ngày tại Việt Nam bằng mô hình K-means tích hợp Random Forest

## Dữ liệu
Dữ liệu bao gồm toàn bộ dữ liệu gốc cũng như dữ liệu đã được làm sạch và xử lý. Để tiện cho việc sử dụng, tất cả dữ liệu sẽ được lưu trữ ở [đây](https://drive.google.com/drive/folders/1uoh64dOepEHd9GR2ZywnCo-8zqMSg5Qn)

Dữ liệu được chia làm 3 folder chính:

Thư mục **original_data**: Chứa dữ liệu thu thập được từ các nguồn được cung cấp và chưa qua xử lý

Thư mục **data_processed**: Chứa dữ liệu đã qua xử lý và làm sạch. Thư mục bao gồm 2 file dữ liệu, đó là file dữ liệu đã được scale và dữ liệu chưa được scale

Thư mục **data_to_predict_and_draw**: Chứa dữ liệu thu thập được trên toàn bản đồ của từng đặc trưng để dự đoán các điểm khác trên bản đồ. Thư mục gồm các file zip của từng đặc trưng, mỗi file bao gồm giá trị của đặc trưng đó tại mỗi vị trí kinh độ và vĩ độ trên toàn bản đồ Việt Nam.

## Mô hình
Trong bài toán này, chúng em đã sử dụng 2 mô hình chính đó là K-means Clustering và Random Forest để dự đoán mật độ NO2. 

Với mô hình K-means, chúng em đã thực hiện chia cụm trên 2 bộ dữ liệu, đó là bộ dữ liệu đã scale và chưa scale.

Với mô hình Random Forest, chúng em đã thực hiên thử nghiệm ở các độ sâu từ 1 đến 200, sau đó sử dụng [KFold Cross Validation](https://machinelearningmastery.com/k-fold-cross-validation/) với K = 10 để tìm ra độ sâu tốt nhất cho mô hình.

Mô hình Linear Regression qua thử nghiệm thể hiện khá kém, do còn đơn giản và không phục vụ tốt cho bài toán phức tạp với nhiều trường dữ liệu. Do đó, chúng em sẽ tập trung chủ yếu vào việc thử nghiệm với mô hình Random Forest.

## Kết quả 
Các mô hình đã được thử nghiệm huấn luyện trên 2 bộ dữ liệu đã scale và chưa scale, kết hợp với việc dùng thêm trường dữ liệu **cluster** sau khi áp dụng K-means và không dùng trường dữ liệu **cluster**. Kết quả cho thấy mô hình thể hiện tốt nhất khi huấn luyện trên bộ dữ liệu có trường dữ liệu cluster và đã được scale. Mô hình huấn luyện trên bộ dữ liệu không có trường cluster và không được scale thể hiện không tốt bằng, tuy nhiên sự chênh lệch là không đáng kể. 

Scale | Thêm trường dữ liệu cluster | Đầy đủ trường dữ liệu | RMSE | R2 | MAPE
--- | --- | --- | --- |--- | ---
Có | Có | Có | 8.26529 | 0.69917 | 34.30465
Có | Có | Không |9.57397 | 0.59624 | 29.31133
Có | Không | Không | 9.61365 | 0.59333 | 27.3513
Không | Không | Không | 9.61902 | 0.5923| 29.22658

## Cài đặt
Môi trường khuyến nghị sử dụng: [Google Colab](https://colab.research.google.com/notebooks/). Đây là môi trường làm việc của Google cho phép ta tận dụng CPU và GPU online mà không cần yêu cầu quá cao về phần cứng của cá nhân. Đồng thời dữ liệu cũng sẽ được lấy từ Google Drive để thuật tiện cho việc sử dụng. 

Do các dữ liệu liên quan đến bài toán đã được lưu ở trên [Drive](https://drive.google.com/drive/folders/1uoh64dOepEHd9GR2ZywnCo-8zqMSg5Qn) để thuận tiện cho việc tái sử dụng, người dùng chỉ cần thay thế các đường dẫn đến file dữ liệu thích hợp để có thể sử dụng code.

Nếu muốn chạy code trên ở máy cục bộ, ta cần phải tải xuống các dữ liệu cần thiết ở [đây](https://drive.google.com/drive/folders/1uoh64dOepEHd9GR2ZywnCo-8zqMSg5Qn), sau đó thay đổi đường dẫn đến các file dữ liệu và sử dụng code.

## Phân chia công việc

| STT | Thành Viên          | Công Việc                                                                                                                                                                                                            |
|-----|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | Đặng Quốc Khánh     | Đọc hiểu bài báo  <br>Tìm hiểu phương pháp giải quyết  <br>Thu thập và ghép dữ liệu với bản đồ  <br>Viết báo cáo và làm slide thuyết trình  <br>Vẽ bản đồ NO2                                           |
| 2   | Nguyễn Phúc Hải     | Đọc hiểu bài báo <br>Tìm hiểu phương pháp giải quyết <br>Viết báo cáo và làm slide thuyết trình <br>Phân tích và xử lý dữ liệu <br> Code mô hình K-means Clustering <br>Tổng hợp dữ liệu và các code thành bản hoàn chỉnh |
| 3   | Phan Quang Hùng     | Đọc hiểu bài báo <br>Tìm hiểu phương pháp giải quyết <br>Viết báo cáo và làm slide thuyết trình <br>Tìm hiểu và phân tích các đặc trưng trong dữ liệu <br>Tìm hiểu về phương pháp đánh giá mô hình                   |
| 4   | Nguyễn Trường Giang | Đọc hiểu bài báo <br>Tìm hiểu phương pháp giải quyết <br>Viết báo cáo và làm slide thuyết trình <br>Code mô hình Random Forest và Linear Regression <br>Thử nghiệm các mô hình khác nhau <br> Vẽ bản đồ NO2               |
| 5   | Lê Hữu Chung        | Đọc hiểu bài báo <br>Tìm hiểu phương pháp giải quyết <br>Viết báo cáo và làm slide thuyết trình <br>Code mô hình Random Forest và Linear Regression <br>Thử nghiệm các mô hình khác nhau                             |                      |

# Liên hệ:
Nguyễn Phúc Hải (me): [Github](https://github.com/HaiNguyen2903)

Nguyễn Trường Giang: [Github](https://github.com/ntg552000)

Lê Hữu Chung: [Github](https://github.com/chungle1504)

Đặng Quốc Khánh: [Github](https://github.com/snowiceheart2000)

Phan Quang Hùng: [Github](https://github.com/phanquanghung)
