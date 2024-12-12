```golang
1. Hướng lập trình
	•	Go: Ngôn ngữ thủ tục và lập trình song song.
	•	Python: Hỗ trợ lập trình hướng đối tượng, thủ tục, và hàm.

Ví dụ:

// Go procedural example
package main

import "fmt"

func add(a, b int) int {
    return a + b
}

func main() {
    fmt.Println(add(2, 3)) // Output: 5
}

# Python procedural example
def add(a, b):
    return a + b

print(add(2, 3))  # Output: 5

2. Quản lý bộ nhớ
	•	Go: Tự động thu gom rác (garbage collection).
	•	Python: Tự động thu gom rác và quản lý bộ nhớ qua reference counting.

Ví dụ:

// Go: Memory managed automatically
package main

import "fmt"

func main() {
    arr := []int{1, 2, 3}
    fmt.Println(arr)
}

# Python: Memory managed automatically
arr = [1, 2, 3]
print(arr)

3. Con trỏ
	•	Go: Có hỗ trợ con trỏ nhưng không hỗ trợ pointer arithmetic.
	•	Python: Không hỗ trợ con trỏ.

Ví dụ (Go):

package main

import "fmt"

func main() {
    var x int = 42
    var p *int = &x
    fmt.Println(*p) // Output: 42
}

Python không sử dụng con trỏ, nhưng bạn có thể đạt được chức năng tương tự với các đối tượng tham chiếu.

4. Xử lý lỗi
	•	Go: Sử dụng error và cơ chế panic/recover.
	•	Python: Sử dụng try/except để xử lý ngoại lệ.

Ví dụ:

// Go: Error handling
package main

import (
    "errors"
    "fmt"
)

func divide(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("cannot divide by zero")
    }
    return a / b, nil
}

func main() {
    result, err := divide(10, 0)
    if err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("Result:", result)
    }
}

# Python: Exception handling
def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

try:
    result = divide(10, 0)
except ValueError as e:
    print("Error:", e)

5. Hiệu năng
	•	Go: Tối ưu hóa cao với mã máy, tốc độ nhanh.
	•	Python: Hiệu năng thấp hơn do chạy trên interpreter.

6. Goroutines và Threading
	•	Go: Sử dụng goroutines và channels để hỗ trợ xử lý song song.
	•	Python: Sử dụng threading hoặc asyncio.

Ví dụ:

// Go: Goroutines
package main

import (
    "fmt"
    "time"
)

func say(msg string) {
    for i := 0; i < 3; i++ {
        fmt.Println(msg)
        time.Sleep(100 * time.Millisecond)
    }
}

func main() {
    go say("hello")
    say("world")
}

# Python: Threading
import threading
import time

def say(msg):
    for _ in range(3):
        print(msg)
        time.sleep(0.1)

thread = threading.Thread(target=say, args=("hello",))
thread.start()
say("world")
thread.join()

7. Thư viện
	•	Go: Sử dụng hệ thống module (go mod) và các package mạnh mẽ.
	•	Python: Thư viện phong phú, với cộng đồng hỗ trợ rộng rãi thông qua pip.

8. Type System
	•	Go: Hệ thống kiểu tĩnh, mạnh mẽ.
	•	Python: Hệ thống kiểu động.

Ví dụ:

// Go: Static typing
package main

import "fmt"

func add(a int, b int) int {
    return a + b
}

func main() {
    fmt.Println(add(2, 3))
}

# Python: Dynamic typing
def add(a, b):
    return a + b

print(add(2, 3))

Kết luận

Đặc điểm	Golang	Python
Hướng lập trình	Thủ tục, song song	Đa năng (OOP, thủ tục, hàm)
Hiệu năng	Nhanh	Chậm hơn
Kiểu dữ liệu	Tĩnh	Động
Quản lý bộ nhớ	Tự động (Garbage Collection)	Tự động (Garbage Collection)
Xử lý đồng thời	Goroutines	Threading/asyncio
Hỗ trợ thư viện	Tốt	Phong phú, phổ biến

Go phù hợp với các ứng dụng cần hiệu năng cao và dễ bảo trì, trong khi Python lý tưởng cho prototyping và các ứng dụng có logic phức tạp hơn.


```