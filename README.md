# Báo cáo: 23810310152-NguyenHao-BagistoHeadless

## Thông tin sinh viên
- Họ và tên: Nguyễn Thị Hảo
- MSSV: 23810310152

## P1: Cài đặt hệ thống (Admin)
![Admin Panel](media/admin.png)

## P2: Khai thác GraphQL API
![GraphQL Query](media/graphql.png)

## P3: Frontend hiển thị sản phẩm
![Frontend](media/frontend.png)

---

## Câu hỏi tự luận

**Q1: So sánh REST API vs GraphQL về Payload**  
-REST API trả toàn bộ dữ liệu từ endpoint, bao gồm các trường mà có thể không cần sử dụng trong frontend. Vì vậy, payload (dữ liệu truyền về) thường lớn, gây tốn băng thông, đặc biệt khi dữ liệu nhiều hoặc có các trường liên quan đến các quan hệ khác (nested data).
-GraphQL cho phép chỉ lấy những trường cần thiết cho giao diện hiển thị. Ví dụ, nếu frontend chỉ cần name và price của sản phẩm, GraphQL chỉ trả đúng 2 trường đó thay vì tất cả thông tin sản phẩm. Điều này giúp payload nhỏ hơn, giảm băng thông và tăng tốc độ tải dữ liệu, đồng thời tối ưu hiệu năng cho ứng dụng.

**Q2: Thay đổi giá sản phẩm qua Headless API dùng Query hay Mutation? Tại sao?**  
-Khi muốn thay đổi dữ liệu trên server, ví dụ cập nhật giá sản phẩm, phải dùng Mutation trong GraphQL.
-Lý do: trong GraphQL, Query chỉ dùng để lấy (read) dữ liệu, không được phép thay đổi trạng thái của server. Mutation là loại hành động chuyên để tạo mới, cập nhật hoặc xóa dữ liệu, đảm bảo server nhận biết đây là thao tác có tác động. Ví dụ, Mutation sẽ gửi thông tin id sản phẩm và new price lên server để thay đổi giá, và server sẽ phản hồi lại dữ liệu mới của sản phẩm sau khi cập nhật.
