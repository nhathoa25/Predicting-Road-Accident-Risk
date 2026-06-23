# Predicting Road Accident Risk

## Tổng quan
Dự án này sử dụng mô hình hồi quy tuyến tính (`Linear Regression`) để dự đoán chỉ số rủi ro tai nạn giao thông (`accident_risk`). Dữ liệu được xử lý từ thông tin về đường, thời tiết, chi tiết chiếu sáng và thời điểm xảy ra.

Notebook chính: `Predicting_Road_Accident_Risk.ipynb`

## Mục tiêu
- Khám phá dữ liệu và trực quan hoá các biến quan trọng.
- Tiền xử lý dữ liệu: chuyển đổi dữ liệu boolean, mã hóa categorical và loại bỏ các biến ít ảnh hưởng.
- Tính ma trận tương quan trên toàn bộ feature đã được xử lý.
- Huấn luyện và đánh giá mô hình `LinearRegression` bằng R², MAE, MSE, RMSE.

## Dữ liệu
Tệp dữ liệu chính: `Predicting_Road_Accident_Risk.csv`

Các cột quan trọng:
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
- `accident_risk` (target)

## Quy trình xử lý
1. Đọc dữ liệu và kiểm tra thông tin.
2. Khám phá dữ liệu bằng biểu đồ phân phối và pairplot.
3. Chuyển đổi cột boolean sang số: `True` → `1`, `False` → `0`.
4. Mã hóa biến phân loại bằng One-Hot Encoding.
5. Tính ma trận tương quan trên toàn bộ dữ liệu đã mã hóa.
6. Loại bỏ các feature có tương quan yếu với `accident_risk` (ngưỡng có thể điều chỉnh).
7. Chia dữ liệu thành tập huấn luyện và kiểm tra.
8. Huấn luyện mô hình và đánh giá bằng các chỉ số phù hợp.

## Kết quả hiện tại
- Các feature có ảnh hưởng mạnh nhất: `curvature`, `lighting_night`, `speed_limit`, `lighting_dim`, `num_reported_accidents`.
- Các feature bị loại bỏ do tương quan yếu: `road_type_rural`, `time_of_day_evening`, `time_of_day_morning`, `num_lanes`, `school_season`, `road_signs_present`.
- Notebook đánh giá cả R² trên tập train và tập test.

## Cài đặt và chạy
1. Tạo môi trường ảo (tuỳ chọn):
   ```bash
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```
2. Cài đặt các thư viện:
   ```bash
   pip install -r requirements.txt
   ```
3. Mở `Predicting_Road_Accident_Risk.ipynb` và chạy theo các cell trong notebook.

## Thư mục và file
- `Predicting_Road_Accident_Risk.ipynb`: Notebook chính chứa toàn bộ quy trình tiền xử lý, mô hình và đánh giá.
- `Predicting_Road_Accident_Risk.csv`: Dữ liệu đã làm sạch dùng để xây dựng mô hình.
- `Cleaned_Road_Accident_Risk.csv`: Dữ liệu sạch dùng trong notebook.
- `requirements.txt`: Danh sách thư viện cần cài đặt.

## Ghi chú
- Notebook hiện tại chia dữ liệu thành 99% train và 1% test.
- Nếu cần, có thể điều chỉnh ngưỡng loại bỏ feature hoặc tỷ lệ train/test để cải thiện kết quả.
- Ma trận tương quan được tính sau khi xử lý dữ liệu để đảm bảo không bỏ sót các feature boolean/categorical.