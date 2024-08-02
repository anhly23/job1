# Sử dụng một hình ảnh Python chính thức làm ảnh nền
FROM python:3.12-alpine

# Đặt thư mục làm việc trong container
WORKDIR /app

# Sao chép nội dung thư mục hiện tại vào container tại /app
COPY . /app

# Cài đặt các phụ thuộc
RUN pip install --no-cache-dir flask gunicorn

# Sao chép tệp requirements.txt và cài đặt các phụ thuộc
COPY requirements.txt .
RUN pip install -r requirements.txt

# Mở cổng 5000 cho bên ngoài container
EXPOSE 5000

# Định nghĩa lệnh để chạy ứng dụng với Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
