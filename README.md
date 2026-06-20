# Predicting Road Accident Risk

## Tổng quan
Dự án này sử dụng học máy tuyến tính (`Linear Regression`) để dự đoán chỉ số nguy cơ tai nạn giao thông (`accident_risk`) dựa trên các đặc trưng về đường, điều kiện thời tiết và thời điểm trong ngày.

Notebook chính: `Predicting_Road_Accident_Risk.ipynb`

## Mục tiêu
- Khám phá và trực quan hóa dữ liệu tai nạn giao thông.
- Tiền xử lý dữ liệu: loại bỏ biến không quan trọng, mã hóa biến phân loại và biến boolean.
- Huấn luyện mô hình hồi quy tuyến tính để dự đoán mức độ rủi ro.
- Đánh giá mô hình bằng các chỉ số: R-squared, MAE, MSE, RMSE.

## Dữ liệu
Tệp dữ liệu: `Predicting_Road_Accident_Risk.csv`

Các cột chính:
- `id`
- `road_type`
- `num_lanes`
- `curvature`
- `speed_limit`
- `lighting`
- `weather`
- `road_signs_present`
- `public_road`
- `time_of_day`
- `holiday`
- `school_season`
- `num_reported_accidents`
- `accident_risk` (biến mục tiêu)

## Các bước thực hiện
1. Nhập các thư viện: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`.
2. Đọc và khám phá dữ liệu.
3. Hiển thị thống kê cơ bản và biểu đồ phân phối.
4. Tính ma trận tương quan và lựa chọn biến quan trọng.
5. Mã hóa biến boolean và biến phân loại bằng One-Hot Encoding.
6. Tách dữ liệu thành `X` và `y`, sau đó chia thành tập huấn luyện và kiểm tra.
7. Huấn luyện mô hình `LinearRegression`.
8. Đánh giá kết quả dự đoán và kiểm tra giả thiết hồi quy.

## Cài đặt và chạy
1. Tạo môi trường ảo (tuỳ chọn):
   ```bash
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```
2. Cài đặt thư viện:
   ```bash
   pip install -r requirements.txt
   ```
3. Mở và chạy notebook `Predicting_Road_Accident_Risk.ipynb` bằng Jupyter Notebook hoặc VS Code.

## Kết quả chính
- Mô hình hồi quy tuyến tính được huấn luyện từ dữ liệu đã tiền xử lý.
- Hiển thị trực quan quan hệ giữa các đặc trưng quan trọng và `accident_risk`.
- Đánh giá mô hình bằng đồ thị dự đoán so với thực tế, phân phối sai số và scatter plot residuals.

## Ghi chú
- Dữ liệu có chứa nhiều biến phân loại và boolean nên cần mã hóa trước khi huấn luyện.
- Tỷ lệ chia dữ liệu trong notebook là 99% train và 1% test.
- Có thể điều chỉnh ngưỡng tương quan và số lượng biến giữ lại để cải thiện mô hình.
