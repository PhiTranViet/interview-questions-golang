- Golang
+ Go is a procedural and concurrent programming language
+ Go does not contain automatic garbade collection for allocating memory
+ Go languages contains pointers but does not contain arithmetic pointers
+ In Go languages map is passed by reference 
+ It does not use header files. Instead of header file go use packages. It uses import to import external packages.
+ It does not support implicit typr conversion
+ It does not support function overloading and also does not suppport user defined operations
+ It does not support const or volatile qualifiers.
+ It provides nil for invalid pointers.
+ Go use panic and recover for resolving error.
+ Go contains goroutines and channel.
+ Go does not support inheritance. But it provides an alternative in the form of Embedding.
- C++
+ C++ is an object oriented programming language
+ C++ does contain classes with constructor and destructors
+ C++ languages does not provide automatic garbage collection for allocating memory.
+ C++ languages contains both pointers as well as arithmetic pointers.
+ In C++ map is passed by value
+ It contains header file and does not contain package.
+ It support implicit type conversion
+ It support function overloading and also support user defined operators.
+ It supports const an volatile qualifier.
+ It provides null or 0 or nullptr for invalid ponters.
+ C++ use try cat and throw for resolving error.
+ It has while or do-while statements.
+ It is less strong typed as compare to Go language
+ C++ has threads
+ C++ supports inheritance.



Vietnamese explanation
Dưới đây là giải thích chi tiết từng điểm so sánh giữa Go và C++ cùng ví dụ minh họa:

1. Hướng lập trình
	•	Go: Ngôn ngữ thủ tục và hỗ trợ lập trình song song.
	•	C++: Ngôn ngữ hướng đối tượng.

Ví dụ:
```golang
// Go procedural example
package main

import "fmt"

func add(a, b int) int {
    return a + b
}

func main() {
    fmt.Println(add(2, 3)) // Output: 5
}
```
```c++

// C++ object-oriented example
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }
};

int main() {
    Calculator calc;
    cout << calc.add(2, 3) << endl; // Output: 5
}
```
2. Class và Constructor/Destructor
	•	Go: Không có class.
	•	C++: Có class và hỗ trợ constructor/destructor.

Ví dụ:
```golang

// Go: Struct instead of Class
package main

import "fmt"

type Person struct {
    name string
}

func (p *Person) greet() {
    fmt.Println("Hello, my name is", p.name)
}

func main() {
    p := Person{name: "Alice"}
    p.greet()
}
```
```c++
// C++: Class with constructor and destructor
#include <iostream>
using namespace std;

class Person {
    string name;
public:
    Person(string n) : name(n) { 
        cout << "Person created: " << name << endl;
    }
    ~Person() {
        cout << "Person destroyed: " << name << endl;
    }
    void greet() {
        cout << "Hello, my name is " << name << endl;
    }
};

int main() {
    Person p("Alice");
    p.greet();
}
```
3. Quản lý bộ nhớ
	•	Go: Tự động thu gom rác (garbage collection).
	•	C++: Không có garbage collection, cần giải phóng bộ nhớ thủ công.

Ví dụ:
```golang

// Go: Memory managed automatically
package main

import "fmt"

func main() {
    arr := []int{1, 2, 3}
    fmt.Println(arr)
}
```
```c++
// C++: Manual memory management
#include <iostream>
using namespace std;

int main() {
    int* arr = new int[3]{1, 2, 3};
    for (int i = 0; i < 3; i++) {
        cout << arr[i] << " ";
    }
    delete[] arr; // Manual cleanup
    return 0;
}
```
4. Con trỏ
	•	Go: Có con trỏ nhưng không hỗ trợ pointer arithmetic.
	•	C++: Hỗ trợ cả con trỏ và pointer arithmetic.

Ví dụ:
```golang

// Go: Pointer usage
package main

import "fmt"

func main() {
    var x int = 42
    var p *int = &x
    fmt.Println(*p) // Output: 42
}
```
```c++
// C++: Pointer arithmetic
#include <iostream>
using namespace std;

int main() {
    int arr[3] = {1, 2, 3};
    int* p = arr;
    cout << *p << " ";   // Output: 1
    cout << *(p + 1) << " "; // Output: 2
    return 0;
}
```
5. Map và Tham chiếu
	•	Go: Map được truyền theo tham chiếu.
	•	C++: Map được truyền theo giá trị mặc định (có thể truyền tham chiếu nếu muốn).

Ví dụ:
```golang

// Go: Map by reference
package main

import "fmt"

func updateMap(m map[string]int) {
    m["a"] = 42
}

func main() {
    m := map[string]int{"a": 1, "b": 2}
    updateMap(m)
    fmt.Println(m) // Output: map[a:42 b:2]
}
```
```c++
// C++: Map by value vs reference
#include <iostream>
#include <map>
using namespace std;

void updateMap(map<string, int>& m) { // Pass by reference
    m["a"] = 42;
}

int main() {
    map<string, int> m{{"a", 1}, {"b", 2}};
    updateMap(m);
    cout << m["a"] << endl; // Output: 42
}
```
6. Header File vs Package
	•	Go: Không dùng header file, thay bằng package.
	•	C++: Dùng header file.

Ví dụ:
```golang

// Go: Import package
package main

import "fmt"

func main() {
    fmt.Println("Hello, Go!")
}
```
```c++
// C++: Include header file
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, C++!" << endl;
    return 0;
}
```
7. Các tính năng khác
	•	Go:
	•	Không hỗ trợ kế thừa, nhưng có embedding.
	•	Không có vòng lặp while hoặc do-while, thay bằng for.
	•	Hỗ trợ goroutines để xử lý đồng thời.
	•	C++:
	•	Hỗ trợ đầy đủ tính năng hướng đối tượng, bao gồm kế thừa.
	•	Có vòng lặp while, do-while.
	•	Sử dụng thread để xử lý đồng thời.

Ví dụ về goroutine (Go) và thread (C++):
```golang

// Go: Goroutines
package main

import (
    "fmt"
    "time"
)

func say(msg string) {
    for i := 0; i < 5; i++ {
        fmt.Println(msg)
        time.Sleep(100 * time.Millisecond)
    }
}

func main() {
    go say("hello")
    say("world")
}
```
```c++
// C++: Threads
#include <iostream>
#include <thread>
using namespace std;

void say(string msg) {
    for (int i = 0; i < 5; i++) {
        cout << msg << endl;
    }
}

int main() {
    thread t1(say, "hello");
    say("world");
    t1.join(); // Wait for thread t1 to finish
}
```