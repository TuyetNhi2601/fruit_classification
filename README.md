# PTUDMayHoc
Báo cáo cuối kỳ nhóm 1 môn Phát triển ứng dụng học máy

## Mô tả

Xây dựng một phần mềm Android có tên “G2 App” nhận dạng trái cây thông qua hình ảnh. Sử dụng TensorflowFlite và Keras để xây dựng và train model, sử dụng công cụ Android Studio và Google Colab để lập trình. 

## Dữ liệu
Tự xây dựng một Dataset trái cây. Có 7 loại trái cây được gắn nhãn và train tương ứng với 7 lớp, bao gồm: Cam, dâu, dưa hấu, nho, chuối, táo, chanh. Người dùng có thể chọn ảnh từ thư viện trên điện thoại để nhận dạng hoặc mở camera để chụp lại hình ảnh 1 trong 7 loại quả trên để nhận dạng. App sẽ dựa vào model đã học được để dự đoán và đưa ra kết quả là tên của loại quả trong hình.
### Cấu trúc dữ liệu.
 
Bộ dữ liệu dùng để train sẽ có 3 thư mục:
Thư mục train: Chứa 7 thư mục con là 7 loại trái cây. Mỗi thư mục có khoảng 450 hình dùng để train.
-	Thư mục validation: Chứa 7 thư mục con. Mỗi thư mục có khoảng 200 hình dùng cho validation.
-	Thư mục test: Chứa 7 thư mục con. Mỗi thư mục chứa khoảng 50 hình dùng cho việc test.

![image](https://user-images.githubusercontent.com/122681319/228914525-2fc2e2fb-c3e7-49b4-8201-c34e20c31cbb.png)

### Xây dựng mô hình và ứng dụng.
Xây dựng models bằng mô hình CNN Sequential.
-	Khởi tạo models Sequential().
-	Tạo Convolutional Layer để lấy các đặc trưng từ ảnh.
-	Dùng Pooling Layer để giảm param khi train, nhưng vẫn giữ được đặc trưng của ảnh.
-	Cho qua 3 lớp Conv2D và MaxPooling2D để lấy đặc trưng.
-	Qua một lớp flatten để làm phẳng. Một layer Dense với số class là 7.
Bắt đầu train model với tập train và validation, có epochs bằng 10.

![image](https://user-images.githubusercontent.com/122681319/228914942-991209ef-8994-4098-91c7-43e99eae16b8.png)

Đánh giá mô hình.

![image](https://user-images.githubusercontent.com/122681319/228915093-d887e126-3682-42fc-aaa5-45fd46139c6f.png)

### Xây dựng ứng dụng.
* Xây dựng ứng dụng trên Android Studio
* Giao diện phần mềm.

![image](https://user-images.githubusercontent.com/122681319/228916224-907ca37b-2582-4dea-a991-c9b92e154281.png)

## Kết quả Demo
* App dự đoán chính xác dưa hấu và cam qua ảnh tải lên.
![image](https://user-images.githubusercontent.com/107638860/203271127-ca971a10-31f1-4eb7-844f-4919754ebfc9.png)
![image](https://user-images.githubusercontent.com/107638860/203271162-736d0f50-010e-48dd-8f5d-d69bcb9827ef.png)

* Nhận dạng chính xác qua ảnh chụp từ camera.

![image](https://user-images.githubusercontent.com/122681319/228916634-d9af20cd-73ce-4282-b616-1061eec9443d.png)


