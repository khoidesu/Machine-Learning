<br />
<div align="center">
  <h1 align="center">Project 2</h1>
  <p align="center">
    <h2>Phân loại khả năng mắc bệnh tim dựa vào các triệu chứng</h2>
    <br />
  </p>
</div>

[![Python 3.11](https://shields.io/badge/python-3.11+-blue)](https://shields.io/badge/python-3.11+-blue)
[![Pytorch](https://img.shields.io/badge/-PyTorch-333?style=flat&logo=pytorch)](https://img.shields.io/badge/-PyTorch-333?style=flat&logo=pytorch)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
[![Numpy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
[![seaborn](https://img.shields.io/badge/seaborn-%230098A4?logo=python&logoColor=white)](https://img.shields.io/badge/seaborn-%230098A4?logo=python&logoColor=white)
[![matplotlib](https://img.shields.io/badge/-Matplotlib-000000?style=flat&logo=python)](https://img.shields.io/badge/-Matplotlib-000000?style=flat&logo=python)
[![]()]()

<!-- ABOUT THE PROJECT -->

## About The Project

Bệnh tim mạch hiện là nguyên nhân gây tử vong hàng đầu trên thế giới, với khoảng 20,5 triệu ca vào năm 2023, chiếm xấp xỉ 32% tổng số ca tử vong toàn cầu [?, ?, ?]. Tại Việt Nam, ước tính của WHO năm 2016 cho thấy 31% trường hợp tử vong có liên quan đến bệnh tim mạch. Dự báo mới nhất cũng chỉ ra rằng 80% gánh nặng tử vong do bệnh tim sẽ rơi vào các quốc gia có thu nhập từ thấp đến trung bình - nơi việc tầm soát và điều trị còn gặp nhiều hạn chế về chi phí và nguồn lực [?, ?].

Trước thực trạng đó, các giải pháp hỗ trợ chẩn đoán sớm và chính xác đóng vai trò vô cùng quan trọng. Trong những năm gần đây, các mô hình học máy (machine learning) đã nổi lên như một hướng tiếp cận hiệu quả, nhờ khả năng xử lý khối lượng dữ liệu lớn và phát hiện các mối quan hệ ẩn giữa các đặc trưng y tế. Đặc biệt, nhiều nghiên cứu đã chứng minh rằng các thuật toán học máy truyền thống như Naive Bayes, K-Nearest Neighbors, Decision Tree... vẫn được ưa chuộng nhờ tính đơn giản, khả năng diễn giải, và độ chính xác chấp nhận được trong thực tế.

### Input

1 list gồm các feature [age, sex, cp, ...] của 1 người

### Ouput

Dự đoán người đó có bị bệnh tim không
1: Có bị bệnh
0: Không bị bệnh

### Dataset

Bộ dữ liệu dự đoán bệnh tim: Cleveland Heart Disease Diagnosis

Bộ dữ liệu gồm 303 bệnh nhân với 14 đặc trưng y tế phản ánh tình trạng sức khỏe tim mạch, bao gồm các thông tin nhân khẩu học (tuổi, giới tính), các chỉ số lâm sàng (huyết áp, cholesterol, nhịp tim tối đa), các kết quả kiểm tra chuyên sâu (điện tâm đồ, mức độ trầm ST, số mạch máu chính) và thông tin về bệnh lý thalassemia. Mỗi đặc trưng đã được mã hóa dạng số để thuận tiện cho việc huấn luyện mô hình.

### Library

- random
- os
- pandas
- numpy
- sklearn
- seaborn
- matplotlib

### Work flow

```
Import data
    |
Discover data
    |
Split data (80% train, 20% test)
    |
Enconder using MinMaxScaler()
    |
KNN, Decision Tree, Naive Bayes train and test accuracy
```

<!-- USAGE EXAMPLES -->

## Report

Accuracy với mỗi thuật toán
| | KNN | Decision Tree | Naive Bayes |
|----------------|--------|---------------|-------------|
| Accuracy score | 90.16% | 86.89% | 85.25% |

Nhận xét:

- KNN cho dự đoán tốt nhất (nhưng neighbor = 85 khá lớn)
- Decision tree nên ưu tiên `recall -> F1 -> Accuracy`

<p align="right">(<a href="#readme-top">back to top</a>)</p>
