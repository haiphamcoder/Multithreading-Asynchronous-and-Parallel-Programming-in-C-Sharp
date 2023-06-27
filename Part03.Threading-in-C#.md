# Threading in C\#

Trong lập trình C#, threading đề cập đến việc sử dụng đa luồng (multithreading) để thực thi các tác vụ đồng thời trong một ứng dụng. Đa luồng cho phép các phần của chương trình chạy đồng thời trên các luồng riêng biệt, mỗi luồng có thể thực hiện một tác vụ độc lập.

Trong C#, bạn có thể sử dụng lớp `Thread` để tạo và quản lý các luồng. Để tạo một luồng mới, bạn có thể khởi tạo một đối tượng `Thread` và chỉ định phương thức mà bạn muốn thực thi trên luồng đó. Sau đó, bạn có thể gọi phương thức `Start()` để bắt đầu thực thi luồng.

Dưới đây là một ví dụ đơn giản về sử dụng luồng trong C#:

```csharp
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        // Tạo một luồng mới và chạy phương thức WorkerMethod trên luồng đó
        Thread thread = new Thread(WorkerMethod);
        thread.Start();

        // Thực hiện công việc khác trên luồng chính
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine("Main Thread: {0}", i);
            Thread.Sleep(1000);
        }

        // Đợi cho luồng phụ hoàn thành trước khi kết thúc chương trình
        thread.Join();
    }

    static void WorkerMethod()
    {
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine("Worker Thread: {0}", i);
            Thread.Sleep(1000);
        }
    }
}
```

Trong ví dụ này, chúng ta tạo một luồng mới và chạy phương thức `WorkerMethod()` trên luồng đó. Đồng thời, luồng chính cũng thực hiện công việc của nó trong vòng lặp. Khi chạy, bạn sẽ thấy các dòng in được đồng thời từ cả hai luồng, cho thấy tính đa luồng trong chương trình.

---

Lưu ý rằng khi làm việc với đa luồng, cần chú ý đến các vấn đề an toàn như đồng bộ hóa truy cập đến dữ liệu chung và tránh các tình huống đua tranh (race conditions).
