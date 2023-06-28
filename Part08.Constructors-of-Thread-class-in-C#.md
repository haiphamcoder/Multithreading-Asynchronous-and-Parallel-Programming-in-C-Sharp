# Các hàm khởi tạo của lớp Thread trong C\#

Lớp Thread trong C# cung cấp các constructor khác nhau để tạo và quản lý các luồng (threads) trong ứng dụng. Dưới đây là mô tả chi tiết về từng constructor và ví dụ cụ thể để minh họa sử dụng của chúng:

## 1. `Thread()`

Constructor Thread() được sử dụng để tạo một đối tượng luồng mới mà không có phương thức được thực thi. Đối tượng luồng này được sử dụng để tạo và quản lý một luồng mới trong ứng dụng. Sau khi tạo đối tượng, bạn có thể gọi phương thức Start() để bắt đầu thực thi luồng.

Ví dụ:

```csharp
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        Thread myThread = new Thread();
        myThread.Start(); // Bắt đầu thực thi luồng
    }
}
```

## 2. `Thread(ThreadStart start)`

Constructor Thread(ThreadStart start) được sử dụng để tạo một đối tượng luồng mới với phương thức ThreadStart được chỉ định để thực thi. Phương thức ThreadStart là một delegate không có tham số và không có giá trị trả về. Khi luồng được bắt đầu, phương thức được chỉ định sẽ được thực thi.

Ví dụ:

```csharp
using System;
using System.Threading;

class Program
{
    static void MyThreadMethod()
    {
        Console.WriteLine("Đây là một luồng mới.");
    }

    static void Main()
    {
        Thread myThread = new Thread(MyThreadMethod);
        myThread.Start(); // Bắt đầu thực thi luồng
    }
}
```

## 3. `Thread(ParameterizedThreadStart start)`

Constructor Thread(ParameterizedThreadStart start) được sử dụng để tạo một đối tượng luồng mới với phương thức ParameterizedThreadStart được chỉ định để thực thi. Phương thức ParameterizedThreadStart là một delegate có một tham số kiểu object và không có giá trị trả về. Khi luồng được bắt đầu, phương thức được chỉ định sẽ được thực thi và tham số được truyền vào.

Ví dụ:

```csharp
using System;
using System.Threading;

class Program
{
    static void MyThreadMethod(object message)
    {
        Console.WriteLine("Đây là một luồng mới với thông điệp: " + message);
    }

    static void Main()
    {
        Thread myThread = new Thread(MyThreadMethod);
        myThread.Start("Xin chào!"); // Bắt đầu thực thi luồng và truyền tham số
    }
}
```

## 4. `Thread(ThreadStart start, int maxStackSize)`

Constructor Thread(ThreadStart start, int maxStackSize) được sử dụng để tạo một đối tượng luồng mới với phương thức ThreadStart và kích thước ngăn xếp tối đa được chỉ định. Tham số maxStackSize xác định kích thước tối đa (theo byte) của ngăn xếp luồng. Nếu tham số này không được chỉ định, kích thước mặc định sẽ được sử dụng.

Ví dụ:

```csharp
using System;
using System.Threading;

class Program
{
    static void MyThreadMethod()
    {
        Console.WriteLine("Đây là một luồng mới.");
    }

    static void Main()
    {
        Thread myThread = new Thread(MyThreadMethod, 1024); // Kích thước ngăn xếp tối đa là 1024 byte
        myThread.Start(); // Bắt đầu thực thi luồng
    }
}
```

## 5. `Thread(ParameterizedThreadStart start, int maxStackSize)`

Constructor Thread(ParameterizedThreadStart start, int maxStackSize) được sử dụng để tạo một đối tượng luồng mới với phương thức ParameterizedThreadStart, kích thước ngăn xếp tối đa và tham số truyền vào. Tham số maxStackSize xác định kích thước tối đa (theo byte) của ngăn xếp luồng. Nếu tham số này không được chỉ định, kích thước mặc định sẽ được sử dụng.

Ví dụ:

```csharp
using System;
using System.Threading;

class Program
{
    static void MyThreadMethod(object message)
    {
        Console.WriteLine("Đây là một luồng mới với thông điệp: " + message);
    }

    static void Main()
    {
        Thread myThread = new Thread(MyThreadMethod, 1024); // Kích thước ngăn xếp tối đa là 1024 byte
        myThread.Start("Xin chào!"); // Bắt đầu thực thi luồng và truyền tham số
    }
}
```

Trên đây là mô tả chi tiết về các constructors của lớp Thread trong C# và các ví dụ cụ thể để minh họa cho từng trường hợp sử dụng.
