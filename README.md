```markdown
 🚗🔍 Phân loại phương tiện giao thông bằng học máy

Đây là bài thực hành sử dụng Python để xây dựng hệ thống **phân loại hình ảnh các phương tiện giao thông** bằng kỹ thuật trích xuất đặc trưng (SIFT) và mô hình học máy (SVM).

---

 📂 Dữ liệu

- Bộ dữ liệu gồm 5 lớp: `bus`, `car`, `moto`, `pedestrian`, `truck`.
- Mỗi lớp là một thư mục chứa các ảnh tương ứng.
- Dữ liệu được lưu trong Google Drive: `/content/drive/MyDrive/class/trainingset`

![Kết quả mô hình](<img width="547" height="469" alt="image" src="https://github.com/user-attachments/assets/42904bbd-6dd4-4818-8532-b16808d2611e" />
)

---

 🔧 Công nghệ sử dụng

| Loại công nghệ      | Thư viện cụ thể                         |
|---------------------|-----------------------------------------|
| Xử lý ảnh           | `OpenCV (cv2)`                          |
| Xử lý dữ liệu       | `numpy`, `matplotlib`, `os`, `pickle`  |
| Học máy             | `scikit-learn` (`KMeans`, `SVM`)        |
| Lưu mô hình         | `pickle`                                |

---

 🚀 Quy trình thực hiện

1. **Tiền xử lý dữ liệu**
   - Đọc và resize ảnh (224x224)
   - Thống kê số ảnh theo nhãn
   - Hiển thị mẫu ảnh

2. **Trích xuất đặc trưng SIFT**
   - Dùng `cv2.SIFT_create()` để lấy keypoints + descriptors

3. **Xây dựng từ điển đặc trưng (Bag of Words)**
   - Gom tất cả descriptors từ tập train → KMeans → Tạo từ điển

4. **Vector hóa ảnh theo mô hình BoW**
   - Mỗi ảnh được biểu diễn thành vector đặc trưng BoW

5. **Huấn luyện mô hình**
   - Chia dữ liệu thành tập train/test
   - Huấn luyện với SVM (Support Vector Machine)
   - Đánh giá accuracy trên cả train và test

6. **Dự đoán ảnh thực tế**
   - Đọc ảnh test → Trích đặc trưng → Dự đoán bằng mô hình

---

 🎯 Kết quả đạt được

- Xây dựng pipeline hoàn chỉnh từ dữ liệu → mô hình → dự đoán ảnh thực tế
- Accuracy (tùy thuộc dữ liệu và thông số) thường đạt từ 80–95%
- Ứng dụng kỹ năng tiền xử lý, trích đặc trưng và mô hình hóa với scikit-learn


![Kết quả mô hình](<img width="404" height="450" alt="image" src="https://github.com/user-attachments/assets/d9417c40-7072-473d-920d-6fc3a87e37ba" />
)
---


 📌 Ghi chú

- Cần chạy trên môi trường có kết nối Google Drive (Google Colab).
- Đảm bảo quyền truy cập thư mục `trainingset` trên Google Drive.
- Có thể cải tiến bằng cách dùng CNN (Convolutional Neural Network) thay cho đặc trưng thủ công.

---
