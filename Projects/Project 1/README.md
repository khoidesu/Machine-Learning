<br />
<div align="center">
  <h1 align="center">Project 1</h1>
  <p align="center">
    <h2>Phân loại chủ đề của 1 bài báo nghiên cứu khoa học dựa vào abstract</h2>
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

Cài đặt chương trình phân loại topic của publication abstract. Chương trình sẽ được xây dựng dựa trên ba phương pháp mã hóa văn bản khác nhau, bao gồm Bag-of-Words (BoW), TF-IDF và Sentence Embeddings. Mỗi phương pháp sẽ được áp dụng với một mô hình phân loại khác nhau, bao gồm Naive Bayes, KNN và Decision Tree.

### Input

Một abstract của publication (bài báo khoa học).

### Ouput

Topic của abstract đó (ví dụ: vật lý, toán học, khoa học máy tính, v.v.).

### Dataset

Trong bài này, chúng ta sẽ sử dụng bộ dữ liệu: https://huggingface.co/datasets/UniverseTBD/arxiv-abstracts-large được cung cấp trên HuggingFace. Bộ dữ liệu này bao gồm các abstract 390 (tóm tắt) của các bài báo khoa học được đăng trên arXiv, một kho lưu trữ trực tuyến cho các bài báo khoa học trong nhiều lĩnh vực khác nhau. Bộ dữ liệu này có thể được sử dụng để phân loại các abstract theo các chủ đề khác nhau hoặc để phân tích nội dung của các bài báo khoa học, bao gồm các thông tin như tiêu đề, tác giả, ngày cập nhật, v.v. Bộ dữ liệu này có kích thước lớn với hơn 2 triệu bản ghi

### Library

- re: Thư viện để làm việc với biểu thức chính quy (regular expressions),
  giúp xử lý và phân tích chuỗi văn bản.
  datasets: Thư viện để tải và làm việc với các bộ dữ liệu từ Hugging
  Face.
- sentence-transformers: Thư viện để tạo và sử dụng các mô hình
- sentence embeddings, giúp chuyển đổi văn bản thành các vector ngữ
  nghĩa.
- matplotlib.pyplot: Thư viện để vẽ đồ thị và biểu đồ, hỗ trợ trực quan
  hóa dữ liệu.
- seaborn: Thư viện để vẽ đồ thị thống kê, cung cấp các hàm tiện ích
  để trực quan hóa dữ liệu một cách đẹp mắt.
- numpy: Cung cấp các đối tượng mảng đa chiều và các hàm toán học
  để làm việc với các mảng này.
- scikit-learn: Thư viện học máy phổ biến, giúp xây dựng và triển khai
  các mô hình học máy phức tạp một cách nhanh chóng.
- pandas: chuẩn hóa dữ liệu

### Work flow

hi

<!-- USAGE EXAMPLES -->

## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
