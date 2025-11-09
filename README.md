## 1. Giới thiệu

Dự án này nhằm thiết kế, mô phỏng và phân tích đặc tính bức xạ của anten bằng phần mềm Altair FEKO 2019.2.
Mục tiêu là tạo ra mô hình anten hoạt động ổn định trong dải tần xác định, có độ lợi cao, hệ số phản xạ thấp, và bức xạ định hướng phù hợp cho các ứng dụng truyền thông không dây.

## 2. Công cụ và phần mềm

Phần mềm sử dụng: Altair FEKO 2019.2 (CADFEKO, POSTFEKO)

Công nghệ mô phỏng: Phương pháp MoM (Method of Moments)

Hệ đơn vị: milimet (mm)

Loại mô hình: 3D electromagnetic simulation

## 3. Cấu trúc thư mục dự án
anten_project/
│
├── model/
│   ├── nhua1.cfx            # Thành phần nhựa số 1 trong cấu trúc anten
│   ├── nhua2.cfx            # Thành phần nhựa số 2
│   ├── nhua3.cfx            # Thành phần nhựa số 3
│   ├── boom.cfx             # Cấu trúc chính (boom) của anten
│   ├── D.cfx                # Cấu trúc phần dẫn điện chính
│   └── Union1.cfx           # Mô hình đã được hợp nhất hoàn chỉnh
│
├── results/
│   ├── antenna.fek          # File kết quả sau khi solver chạy
│   ├── antenna.out          # Log mô phỏng
│   ├── S11_plot.png         # Đồ thị hệ số phản xạ S11
│   ├── Gain_3D.png          # Biểu đồ bức xạ 3D
│   └── Pattern_2D.png       # Biểu đồ bức xạ 2D (mặt cắt)
│
├── docs/
│   ├── antenna_structure.png  # Hình mô hình anten 3D
│   ├── simulation_setup.png   # Hình thiết lập nguồn và port
│   └── README.md              # File mô tả dự án
│
└── nhom_7_anten_after.cfx   # File mô phỏng chính của nhóm

## 4. Cấu trúc mô hình anten

Boom: phần trụ chính giữ các phần tử anten.

D: phần tử dẫn điện (radiating elements).

Nhua1, nhua2, nhua3: lớp vật liệu cách điện hỗ trợ cơ học.

Union1: kết cấu tổng hợp của toàn anten sau khi hợp nhất.

Port: nguồn cấp tín hiệu (feed) được gắn tại vị trí thích hợp.

## 5. Quy trình mô phỏng

Tạo hình học (Geometry): thiết kế anten 3D trong CADFEKO.

Gán vật liệu (Media): gán kim loại dẫn điện và lớp nhựa cách điện.

Thiết lập nguồn (Source): chọn port, kiểu kích thích và tần số.

Yêu cầu kết quả (Request): thêm Far-field, S-parameter và VSWR.

Chia lưới (Meshing): tạo lưới cho mô hình để chuẩn bị solver.

Chạy mô phỏng (Solver): sử dụng FEKO solver để tính toán.

Phân tích kết quả (Post-processing): hiển thị bức xạ, S11, Gain trong POSTFEKO.

## 6. Kết quả mô phỏng (ví dụ)
Thông số	Giá trị	Ghi chú
Tần số hoạt động	2.4 GHz	Băng tần WiFi/IoT
Độ lợi (Gain)	7.8 dBi	Bức xạ định hướng tốt
S11 (Return Loss)	–18 dB	Hiệu quả phản xạ thấp
VSWR	1.3	Khớp trở kháng tốt
Loại anten	Yagi-Uda (hoặc anten thanh trụ)	Tùy mô hình cụ thể
## 7. Kết luận

Anten được mô phỏng thành công với độ lợi cao và phản xạ thấp trong dải tần thiết kế.

Kết quả mô phỏng chứng minh tính khả thi của mô hình, có thể áp dụng cho các ứng dụng WiFi, IoT, hoặc truyền thông không dây tầm ngắn.

Các thông số mô phỏng có thể tiếp tục được tối ưu bằng cách điều chỉnh khoảng cách phần tử, chiều dài dẫn, hoặc vật liệu nền.

## 8. Thành viên thực hiện

Nhóm 7 – Dự án mô phỏng anten

Thành viên: (Điền tên bạn và các thành viên khác nếu có)

Người phụ trách mô phỏng: (Tên bạn)

Phần mềm: Altair FEKO v2019.2

Thời gian thực hiện: (Ví dụ: 10/2025)