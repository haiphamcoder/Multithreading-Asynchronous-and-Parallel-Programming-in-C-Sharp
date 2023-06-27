# MultiTasking (Đa nhiệm)

Đa nhiệm là khả năng của hệ điều hành hoặc môi trường chạy chương trình để thực thi nhiều tác vụ (tasks) đồng thời. Trong môi trường đa nhiệm, có thể có nhiều tác vụ đang chạy song song trên một hệ thống, mỗi tác vụ thực thi một công việc riêng biệt.

Có hai dạng chính của đa nhiệm:

## Preemptive MultiTasking

Trong dạng đa nhiệm này, hệ điều hành hoặc môi trường chạy chương trình quản lý việc chia thời gian (time-sharing) giữa các tác vụ. Mỗi tác vụ được cấp một khoảng thời gian nhất định để thực thi trước khi bị ngắt quỵt và chuyển sang tác vụ khác. Hệ điều hành quản lý và ưu tiên thực thi các tác vụ theo một thuật toán nhất định, tạo cảm giác như các tác vụ đang chạy đồng thời.

## Cooperative MultiTasking

Trong dạng đa nhiệm này, tác vụ hiện tại tự nguyện chuyển quyền điều khiển cho các tác vụ khác. Thay vì hệ điều hành can thiệp và ngắt quỵt tác vụ, tác vụ hiện tại phải tự giải phóng điều khiển và cho phép tác vụ khác thực thi. Hình thức này yêu cầu sự hợp tác từ các tác vụ để đảm bảo rằng không có tác vụ nào "chiếm giữ" quá lâu và gây trì trệ cho hệ thống.

---

Cả hai dạng đa nhiệm đều cho phép thực thi nhiều tác vụ đồng thời, tăng cường hiệu suất và khả năng phản hồi của hệ thống. Trong lập trình C#, bạn có thể tận dụng đa nhiệm bằng cách sử dụng đa luồng (multithreading) hoặc các công nghệ bất đồng bộ (asynchronous) để thực hiện các tác vụ song song và không chặn luồng chính của ứng dụng.
