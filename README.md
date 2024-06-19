# THÔNG TIN CÁ NHÂN
- Họ và tên : Triệu Văn Hiếu
- MSV : K215480106095
# QUẢN LÝ THƯ VIỆN 
# Mô tả bài toán
- Giúp quản lý thư viện dễ dàng hơn và có các chức năng như thêm sửa, xóa, tìm kiếm, cho các bảng tạo trigger để có thể không bị đặt cùng 1 quyển sách tạo cursor để thống kê số sách tồn kho tạo view hiển thị số sách được mượn nhiều nhất và tạo hàm fn tính số sách đã mượn
# Các chức năng:
#### Quản lý người dùng:
- Đăng nhập
- Liệt kê tất cả người dùng
- Thêm người dùng
- Xóa người dùng
- Đổi thông tin người dùng
- Đổi mật khẩu người dùng
- Kiểm tra đăng nhập
#### Quản lý sách:
- Liệt kê tất cả sách
- Thêm sách
- Xóa sách
- Sửa thông tin sách
#### Quản lý mượn trả:
- Thêm phiếu mượn
- Sửa phiếu mượn
- Xóa phiếu mượn
- Thêm chi tiết phiếu mượn
- Cập nhật số lượng chi tiết phiếu mượn
- Xóa dòng chi tiết phiếu mượn
#### Báo cáo:
- Báo cáo sách tồn kho
- Báo cáo nhân viên cho mượn nhiều sách trong tháng
- Báo cáo sách được mượn nhiều nhất trong tháng

# Các bảng của hệ thống
#### Thuthu
-![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/34536b62-70cc-4cde-a32e-d0526e827fae)
- maThuThu (PK): INT - Khóa chính, duy nhất, đại diện cho mã thủ thư.
- ten: NVARCHAR(100) - Tên của thủ thư.
- email: NVARCHAR(100) - Địa chỉ email của thủ thư.
- soDienThoai: NVARCHAR(20) - Số điện thoại của thủ thư.
- diaChi: NVARCHAR(200) - Địa chỉ của thủ thư.
- matKhau: NVARCHAR(50) - Mật khẩu để đăng nhập.
#### NguoiDung
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/f44e6115-a9f2-4e88-8029-a75eaefaf085)
- maNguoiDung (PK): INT - Khóa chính, duy nhất, đại diện cho mã người dùng.
- ten: NVARCHAR(100) - Tên của người dùng.
- email: NVARCHAR(100) - Địa chỉ email của người dùng.
- soDienThoai: NVARCHAR(20) - Số điện thoại của người dùng.
- diaChi: NVARCHAR(200) - Địa chỉ của người dùng.
- loaiThanhVien: NVARCHAR(50) - Loại thành viên (VD: Thường, VIP).
- matKhau: NVARCHAR(50) - Mật khẩu để đăng nhập.
- maThuThu (FK): INT - Khóa ngoại tham chiếu đến bảng ThuThu, xác định thủ thư quản lý người dùng.
#### Sach
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/e9b4e767-98a5-48d7-a100-a5d87cff81a5)
- maSach (PK): INT - Khóa chính, duy nhất, đại diện cho mã sách.
- tenSach: NVARCHAR(100) - Tên của sách.
- tacGia: NVARCHAR(100) - Tác giả của sách.
- theLoai: NVARCHAR(50) - Thể loại của sách.
- namXuatBan: INT - Năm xuất bản của sách.
- nhaXuatBan: NVARCHAR(100) - Nhà xuất bản của sách.
- giaSach: INT - Giá bán của sách.
- soLuongTon: INT - Số lượng tồn kho của sách.
- maThuThu (FK): INT - Khóa ngoại tham chiếu đến bảng ThuThu, xác định thủ thư quản lý sách.
#### PhieuMuon
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/ec29bdc0-0244-4e4d-89e5-9cf1caff4e08)
- maPhieuMuon (PK): INT - Khóa chính, duy nhất, đại diện cho mã phiếu mượn.
- maNguoiMuon (FK): INT - Khóa ngoại tham chiếu đến bảng NguoiDung, xác định người mượn sách.
- maSach (FK): INT - Khóa ngoại tham chiếu đến bảng Sach, xác định sách được mượn.
- ngayMuon: DATE - Ngày mượn sách.
- ngayTra: DATE - Ngày dự kiến trả sách.
- maThuThu (FK): INT - Khóa ngoại tham chiếu đến bảng ThuThu, xác định thủ thư thực hiện giao dịch mượn sách.
#### DatCho
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/304a44e5-5bd8-4da4-9497-d8db8aa52340)
- maDatCho (PK): INT - Khóa chính, duy nhất, đại diện cho mã đặt chỗ.
- maNguoiDung (FK): INT - Khóa ngoại tham chiếu đến bảng NguoiDung, xác định người đặt chỗ.
- maSach (FK): INT - Khóa ngoại tham chiếu đến bảng Sach, xác định sách được đặt chỗ.
- ngayDat: DATE - Ngày đặt chỗ sách.
- ngayLay: DATE - Ngày dự kiến lấy sách.
- maThuThu (FK): INT - Khóa ngoại tham chiếu đến bảng ThuThu, xác định thủ thư thực hiện giao dịch đặt chỗ.
#### YKienKhachHang
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/922d6890-1c04-49d1-9a99-041a7ee04d51)
- maYKien (PK): INT - Khóa chính, duy nhất, đại diện cho mã ý kiến.
- maNguoiDung (FK): INT - Khóa ngoại tham chiếu đến bảng NguoiDung, xác định người đóng góp ý kiến.
- noiDung: NVARCHAR(MAX) - Nội dung ý kiến phản hồi.
- ngayGopY: DATE - Ngày gửi ý kiến.
- maThuThu (FK): INT - Khóa ngoại tham chiếu đến bảng ThuThu, xác định thủ thư quản lý ý kiến phản hồi.
#### Sơ đồ thực thể liên kết
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/5dec1891-ed66-4525-8886-7bdd58918fc9)
#### Thêm các dữ liệu cho bảng
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/ab73dff3-2a5c-46f4-81f2-91d646efd531)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/0f3a2d6e-74b9-4815-9b4f-0394b130671b)
# CÁC CHỨC NĂNG THEO YÊU CẦU 
- Tạo các thủ tục thêm sửa xóa tìm kiếm của các bảng
- Bảng thủ thư
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/cd540a68-405d-4cca-a1fa-2b400072bfaa)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/c35e23cd-2432-4010-922f-2ef1deeeaa2a)
- Thực hiện các thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/02732153-cea1-43be-aa61-7532ac9e9f9c)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/c48f7170-06a1-432a-aaea-c1cf76475c95)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/7126a774-4989-4611-b0c7-144e4a267186)
- Bảng người dùng
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/552cc857-19c3-4b12-a8bb-37d6c45d1173)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/422b5147-2ec6-40dd-8c99-f98872224f11)
- Thực hiện các thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/427aa345-ac4c-4154-89d6-435f36df2a0d)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/7a771fa0-4976-4ffb-9216-a08800e9e77a)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/2249a433-d99c-419d-b2a3-2c2a39ecc7f7)
- Bảng sách
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/169db44a-371e-4eee-a1b0-c02db6ae4e5c)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/abd1bed3-04f6-4863-a25b-3a424208d33b)
- Thực hiện các thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/b201b31b-b2f3-495e-b257-32e5dde363c7)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/efbb791c-62c5-4c75-8953-39195a04e104)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/0b3197e5-4945-4171-b91d-0941fe379f0c)
- Bảng Phiếu mượn
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/da204869-33e1-4101-a164-67175908c1db)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/6037281c-02b0-4a83-9932-a4a1efc9d611)
- Thực hiện các thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/1a4ba017-7f63-4b9e-a1ee-3b710b0c64d8)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/e98844be-ae24-4679-974b-49f581fc9ca0)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/29cf94bb-e892-471c-a3bf-12d7d3e09793)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/e09c764d-e8c8-410a-a720-6ac532332fa8)
- Bảng Đặt Chỗ
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/14cc6dac-4cff-4c0c-8a16-fd9f03506fd1)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/7deda8d3-72fc-450c-8d4a-b2f5caa7a0c2)
- Thực hiện các thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/b8dc60da-9f2f-4c60-a20d-8adc396b4669)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/4fb38c28-6c75-4eb8-ba1f-d155160af163)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/19a81682-b5a5-4441-983c-475afc7b4000)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/5b991639-73ba-48e9-bbd7-c7df4c9b92ec)
- Bảng YKienKhachHang
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/5fa9765d-14bc-47ae-8bde-5ba8b8971dd3)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/839e9510-d096-40c8-b6bf-06d9ec6856c3)
- Thực hiện các thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/f1ab6e4f-141d-4ed7-bb3b-a0c7ba9b91e7)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/298534c0-b5bd-4560-9912-18659772704b)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/d82d6738-ada6-47ec-9002-48a5069a4bca)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/1d116bab-d66d-43ae-b971-8c3b1fa0ef01)
- Một thủ tục Tổng hợp thống kê
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/ece736a4-e299-4bef-8249-73f7a3c73927)
- Thực hiện thủ tục
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/898b54aa-44b5-4107-8eab-3b43537efc18)
#### Chức năng nâng cao 
- Tạo Trigger để ngăn chặn việc đặt trùng sách
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/cbb97599-c86e-4382-aa1e-688848e1639f)
- Chạy Trigger
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/c0d1c453-1258-4af2-88eb-bbf3a8d62d8f)
- Khi chạy ta thấy lỗi và hiển thị lên đã có người đặt chỗ rồi
- Tạo cursor để cập nhật số lượng tồn kho của sách khi có người mượn sách
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/15d8e159-41f0-4cab-ac08-f868182843f2)
- Chạy Cursor
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/aa634f57-5b36-4025-8651-bd33d1e7740a)
- Ta thấy nó se trừ đi số lượng sách đã mượn để ra số lượng tồn
- Tạo một view hiển thị số sách được mượn nhiều nhất
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/d7f8b5b5-41ae-4238-9a91-c570f1fd7f6e)
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/f579581b-716e-45fc-a060-006ae0fa20b4)
- Chạy View
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/65760a3a-696e-4fd4-b54d-e573ce1d902d)
- Đã hiện lên số sách được mượn nhiều 
- Tạo hàm fn để tính tổng số sách đã mượn
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/85c12ff1-ec00-434b-a40a-638c564524c8)
- Kết quả
- ![image](https://github.com/trieuvanhieu/BTLHQTCDDL/assets/168851528/53695d08-6c1c-496f-a7c1-d2069516ddc6)
- Vậy tổng số sách người 2 mượn là 3 quyển
## Cảm ơn thầy đã xem do khả năng co hạn bài còn nhiều sai xót mong thầy có thể góp ý để em sửa ạ cảm ơn thầy ạ

















