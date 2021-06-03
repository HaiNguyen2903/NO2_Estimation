# Ước lượng mật độ NO2 hàng ngày tại Việt Nam bằng mô hình K-means tích hợp Random Forest

## Dữ liệu
Dữ liệu bao gồm toàn bộ dữ liệu gốc cũng như dữ liệu đã được làm sạch và xử lý. Để tiện cho việc sử dụng, tất cả dữ liệu sẽ được lưu trữ ở [đây](https://drive.google.com/drive/folders/1uoh64dOepEHd9GR2ZywnCo-8zqMSg5Qn)
## Mô hình
Trong bài toán này, chúng em đã sử dụng 2 mô hình chính đó là K-means Clustering và Random Forest để dự đoán mật độ NO2. 

Với mô hình K-means, chúng em đã thực hiện chia cụm trên 2 bộ dữ liệu, đó là bộ dữ liệu đã scale và chưa scale.

Với mô hình Random Forest, chúng em đã thực hiên thử nghiệm ở các độ sâu từ 1 đến 200, sau đó sử dụng [KFold Cross Validation](https://machinelearningmastery.com/k-fold-cross-validation/) với K = 10 để tìm ra độ sâu tốt nhất cho mô hình.

## Kết quả 

## Cài đặt
Môi trường khuyến nghị sử dụng: [Google Colab](https://colab.research.google.com/notebooks/). Đây là môi trường làm việc của Google cho phép ta tận dụng CPU và GPU online mà không cần yêu cầu quá cao về phần cứng của cá nhân. Đồng thời dữ liệu cũng sẽ được lấy từ Google Drive để thuật tiện cho việc sử dụng. 

Do các dữ liệu liên quan đến bài toán đã được lưu ở trên [Drive](https://drive.google.com/drive/folders/1uoh64dOepEHd9GR2ZywnCo-8zqMSg5Qn) để thuận tiện cho việc tái sử dụng, người dùng chỉ cần thay thế các đường dẫn đến file dữ liệu thích hợp để có thể sử dụng code.

Nếu muốn chạy code trên ở máy cục bộ, ta cần phải tải xuống các dữ liệu cần thiết ở [đây](https://drive.google.com/drive/folders/1uoh64dOepEHd9GR2ZywnCo-8zqMSg5Qn), sau đó thay đổi đường dẫn đến các file dữ liệu và sử dụng code.
## Mô hình

## Phân chia công việc

<table width="400">
  <tr>
    <td> Thành viên </td>
    <td> Đặng Quốc Khánh </td>
    <td> Nguyễn Phúc Hải </td>
    <td> Phan Quang Hùng </td>
    <td> Nguyễn Trường Giang </td>
    <td> Lê Hữu Chung </td>
  </tr>
  <tr>
    <td></td>
    <td>
       Đọc hiểu bài báo <br>
       Tìm hiểu phương pháp giải quyết <br>
       Thu thập và ghép dữ liệu với bản đồ <br>
       Viết báo cáo và làm slide thuyết trình <br>
       Vẽ bản đồ NO2 ở các mùa 
    </td>    
    <td>
       Đọc hiểu bài báo <br>
       Tìm hiểu phương pháp giải quyết <br>
       Viết báo cáo và làm slide thuyết trình <br>
       Phân tích và xử lý dữ liệu <br>
       Code mô hình K-means Clustering <br>
       Tổng hợp dữ liệu và các code thành bản hoàn chỉnh
    </td> 
    <td>
       Đọc hiểu bài báo <br>
       Tìm hiểu phương pháp giải quyết <br>
       Viết báo cáo và làm slide thuyết trình <br>
       Tìm hiểu và phân tích các đặc trưng trong dữ liệu <br>
       Tìm hiểu về phương pháp đánh giá mô hình
    </td>
    <td>
       Đọc hiểu bài báo <br>
       Tìm hiểu phương pháp giải quyết <br>
       Viết báo cáo và làm slide thuyết trình <br>
       Code mô hình Random Forest và Linear Regression <br>
       Thử nghiệm các mô hình khác nhau <br>
       Vẽ bản đồ NO2 
    </td>
    <td>
       Đọc hiểu bài báo <br>
       Tìm hiểu phương pháp giải quyết <br>
       Viết báo cáo và làm slide thuyết trình <br>
       Code mô hình Random Forest và Linear Regression <br>
       Thử nghiệm các mô hình khác nhau
    </td> 
  </tr>
</table>

# Liên hệ:
Nguyễn Phúc Hải (me): [Github](https://github.com/HaiNguyen2903)

Nguyễn Trường Giang: [Github](https://github.com/ntg552000)

Lê Hữu Chung: 

Đặng Quốc Khánh: [Github](https://github.com/snowiceheart2000)

Phan Quang Hùng: [Github](https://github.com/phanquanghung)
