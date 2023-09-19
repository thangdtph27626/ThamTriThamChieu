# Tham Chiếu Và Tham Trị Trong Java

Đầu tiên ta cần hiểu tham trị và tham chiếu là gì ?

– Tham trị tức là truyền giá trị
– Tham chiếu tức là chiếu đến 1 địa chỉ

## Tham trị (passed by value) trong Java

– Kiểu này dành cho các biến, các tham số khai báo kiểu dữ liệu cơ bản nguyên thủy gồm : byte, short, int, long, float, double, char.

– Nếu chúng ta gọi một phương thức và truyền một giá trị cho phương thức đó được gọi là truyền giá trị. Việc thay đổi giá trị chỉ có hiệu lực trong phương thức được gọi, không có hiệu lực bên ngoài phương thức. Vì nó chỉ tác động đến bản sao giá trị  chứ không phải là địa chỉ nó trong bộ nhớ
Ví dụ :

```
public class Foo {
    int value = 10;

    Foo(){};
    void change(int value) {
        value += 10;
    }
 
    public static void main(String args[]) {
        Foo obj = new Foo();
 
        System.out.println("Trước khi thay đổi: " + obj.value);
        op.change(10);
        System.out.println("Sau khi thay đổi: " + obj.value);
    }
}
//Trước khi thay đổi: 50
//Sau khi thay đổi: 50
```

## Tham chiếu (passed by reference) trong Java

– Khi chúng ta gọi một phương thức và truyền một tham chiếu cho phương thức đó được gọi là truyền tham chiếu. Việc thay đổi giá trị của biến tham chiếu bên trong phương thức làm thay đổi giá trị gốc của nó.

– Trong Java, có thể dùng biến tham chiếu vì nó lưu địa chỉ đối tượng được lưu trong bộ nhớ Heap nhưng biến tham chiếu được lưu trong bộ nhớ Stack
Ví dụ :

```
public class Person {
    private String Name;
    private int Age;

    public Person(String name) {
        this.Name = name;
    }

    public void setAge(int age) {
        this.Age = age;
    }

    public int getAge() {
        return this.Age;
    }

}
public class MyClass {
    public static void main(String[] args) {
        Person person = new Person("John");
        person.setAge(20);
        celebrateBirthday(j);

        System.out.println(person.getAge());
    }

    static void celebrateBirthday(Person p) {
        p.setAge(p.getAge() + 1);
    }
}

//Output: 21
```
