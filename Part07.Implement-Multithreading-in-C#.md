# Triển khai đa luồng trong C\#

Để triển khai đa luồng trong C#, bạn có thể sử dụng các lớp và đối tượng từ namespace System.Threading. Dưới đây là một ví dụ cơ bản về cách triển khai đa luồng trong C# bằng cách sử dụng lớp Thread:

```csharp
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        // Tạo và khởi động một luồng mới
        Thread thread = new Thread(DoWork);
        thread.Start();

        // Thực hiện công việc trong luồng chính
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine("Main thread: " + i);
            Thread.Sleep(1000); // Ngừng 1 giây
        }

        // Chờ cho luồng phụ kết thúc
        thread.Join();

        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }

    static void DoWork()
    {
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine("Worker thread: " + i);
            Thread.Sleep(1000); // Ngừng 1 giây
        }
    }
}
```

Trong ví dụ này, chúng ta tạo một luồng mới bằng cách khởi tạo một đối tượng Thread và truyền phương thức `DoWork` làm tham số vào hàm khởi tạo. Sau đó, chúng ta gọi phương thức `Start` để bắt đầu thực thi luồng mới.

Trong hàm `Main`, chúng ta thực hiện công việc trong luồng chính, in ra thông điệp và ngủ trong 1 giây. Trong luồng phụ, chúng ta cũng thực hiện công việc tương tự. Bằng cách sử dụng phương thức `Thread.Sleep`, chúng ta ngừng mỗi luồng trong 1 giây.

Cuối cùng, chúng ta gọi phương thức `Join` để đảm bảo rằng luồng phụ kết thúc trước khi chương trình kết thúc.

Điều này cho phép chương trình in ra thông điệp của cả luồng chính và luồng phụ đồng thời.
