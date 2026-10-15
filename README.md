# Tái lập bài VN30 + Markowitz

Notebook `vn30_markowitz_replication.ipynb` làm lại bài *New Stocks Prediction Portfolio Optimization on VN30: Machine Learning Method* (Nguyễn Anh Phong & Nguyễn Trúc Linh, Kurdish Studies 2023). DOI: [10.58262/ks.v11i2.425](https://doi.org/10.58262/ks.v11i2.425).

## Chạy

```bash
pip install -r requirements.txt
jupyter notebook   # hoặc upload file .ipynb lên Google Colab rồi Run all vn30_markowitz_replication.ipynb
```

Dữ liệu được tải theo thứ tự: DNSE (giá điều chỉnh, nguồn chính) → CafeF → `vnstock` → `yfinance` → file CSV trong `data/prices/<MÃ>.csv` (cột `date` và `close`). Bảng giá của mỗi nguồn được lưu tạm vào `data/vn30_close_<nguồn>.csv`. Notebook có ô kiểm tra chất lượng dữ liệu (biến động bất thường, giá đứng yên). Hình và bảng kết quả nằm trong `outputs/`.

Đặt biến môi trường `VN30_DATA_SOURCE=demo` để chạy thử bằng dữ liệu mô phỏng (chỉ để kiểm tra code).

## Nội dung

Phần 1–10 làm đúng các bước và đánh số hình như bài. Phần 11 là phần mở rộng: kiểm tra ngoài mẫu (huấn luyện đến 2021, kiểm tra 2022 đến 05/2023), so Sharpe tối đa với các danh mục có trần trọng số, phương sai nhỏ nhất, chia đều top 5 và chia đều VN30.

Các giả định bài không ghi (khoảng thời gian, rổ VN30, lãi suất phi rủi ro 2%) nằm trong phần Cấu hình và có thể đổi.
