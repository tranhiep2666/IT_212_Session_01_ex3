Prompt mới :

Tôi đang review một đoạn code Java dùng để tính thuế VAT 10% cho hóa đơn sản phẩm.

Hãy đóng vai trò là một kỹ sư phần mềm và thực hiện các công việc sau:

Phân tích cả lỗi cú pháp, lỗi runtime và đặc biệt là lỗi logic nghiệp vụ.
Kiểm tra các trường hợp biên (edge cases), nhất là khi biến amount có giá trị âm (amount < 0) hoặc bằng 0 (amount == 0).
Cho biết rủi ro của việc xử lý sai các giá trị này trong hệ thống hóa đơn.
Sửa lại code Java để:
Không cho phép giá trị hóa đơn âm hoặc bằng 0.
Ném ra ngoại lệ phù hợp nếu dữ liệu đầu vào không hợp lệ.
Vẫn tính VAT 10% đối với các giá trị hợp lệ.
Giải thích ngắn gọn lý do thay đổi.
Mã nguồn:
public class TaxCalculator {

    public static double calculateVAT(double amount) {

        return amount * 0.1;

    }

}

Đoạn code Java đã được AI sửa đổi:

public class TaxCalculator {

    public static double calculateVAT(double amount) {
        if (amount <= 0) {
            throw new IllegalArgumentException(
                "Amount must be greater than 0."
            );
        }

        return amount * 0.1;
    }
}

Giải thích ngắn gọn:

Code gốc không có lỗi cú pháp nhưng có lỗi logic nghiệp vụ.
Nếu amount âm, hàm sẽ trả về VAT âm, điều này không hợp lý đối với hóa đơn.
Nếu amount bằng 0, việc tính VAT thường không có ý nghĩa trong ngữ cảnh hóa đơn hợp lệ.
Phiên bản sửa đổi kiểm tra amount <= 0 và ném IllegalArgumentException để ngăn dữ liệu không hợp lệ đi vào hệ thống.