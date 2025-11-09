## 1. Giới thiệu

- Dự án này nhằm thiết kế, mô phỏng và phân tích đặc tính bức xạ của anten bằng phần mềm Altair FEKO 2019.2.
- Mục tiêu là tạo ra mô hình anten hoạt động ổn định trong dải tần 2Ghz - 2.8Ghz, có độ lợi cao, hệ số phản xạ thấp, và bức xạ định hướng phù hợp cho các ứng dụng truyền thông không dây.

## 2. Công cụ và phần mềm

- Phần mềm sử dụng: Altair FEKO 2019.2
- Công nghệ mô phỏng: Phương pháp MoM (Method of Moments)
- Hệ đơn vị: milimet (mm)

## 3. Cấu trúc mô hình anten

### + Hình học (Geometry)

Cây hình học bao gồm tất cả các đối tượng 3D vật lý của mô hình:

* `boom`: Phần trụ chính (boom) của anten, đóng vai trò là khung đỡ cơ học cho tất cả các phần tử khác.
* `D`: Phần tử bức xạ chính (radiating element) của anten.
* `nhua1`, `nhua2`, `nhua3`**: Ba chi tiết bằng nhựa (hoặc vật liệu cách điện), được sử dụng để cố định các phần tử vào boom và cách điện chúng.
* `R`: Một phần tử khác của anten phần tử phản xạ - reflector.
* `Union1`: Một cấu trúc tổng hợp được tạo bằng cách hợp nhất (union) các đối tượng con. Nó bao gồm:
    * `DE1`, `DE2`: Các thành phần con, hai phần của chấn tử (driven element).
    * `Line1`: Một đoạn dây (wire) được sử dụng trong cấu trúc cấp nguồn.

### + Cổng (Ports)

Phần này định nghĩa các nguồn kích thích (nguồn cấp tín hiệu) cho mô hình:
* `Port1`: Điểm cấp nguồn (feed point) duy nhất cho anten. Đây là nơi tín hiệu RF được đưa vào để anten bức xạ.

## 4. Quy trình mô phỏng

- Tạo hình học (Geometry): thiết kế anten 3D trong CADFEKO.
- Gán vật liệu (Media): gán kim loại dẫn điện và lớp nhựa cách điện.
- Thiết lập nguồn (Source): chọn port, kiểu kích thích và tần số.
- Yêu cầu kết quả (Request): thêm Far-field, S-parameter và VSWR.
- Chia lưới (Meshing): tạo lưới cho mô hình để chuẩn bị solver.
- Chạy mô phỏng (Solver): sử dụng FEKO solver để tính toán.
- Phân tích kết quả (Post-processing): hiển thị bức xạ, S11, Gain trong POSTFEKO.

## 5. Kết quả mô phỏng 
### Thông số	        Giá trị     	Ghi chú
#### Tần số hoạt động	2GHz - 2.8Ghz	    Băng tần được sử dụng
#### Độ lợi (Gain)	    5 dB	            Bức xạ định hướng tốt
#### S11 (Return Loss)	–12.5 dB	        Hiệu quả phản xạ thấp
VSWR	4.8	Khớp trở kháng tốt
### Loại anten	Yagi-Uda 

## 6. Kết luận

- Anten được mô phỏng thành công với độ lợi cao và phản xạ thấp trong dải tần thiết kế.
- Kết quả mô phỏng chứng minh tính khả thi của mô hình, có thể áp dụng cho các ứng dụng WiFi, IoT, hoặc truyền thông không dây tầm ngắn.
- Các thông số mô phỏng có thể tiếp tục được tối ưu bằng cách điều chỉnh khoảng cách phần tử, chiều dài dẫn, hoặc vật liệu nền.

## 7. Thành viên thực hiện

Nhóm 7 – Dự án mô phỏng anten
Thành viên: 
### - Lê Quốc Thành ( trưởng nhóm )
### - Trần Thành Đạt 

Người phụ trách mô phỏng: Lê Quốc Thành, Trần Thành Đạt

Phần mềm: Altair FEKO v2019.2

Thời gian thực hiện: ( 10/2024)