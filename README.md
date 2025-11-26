# thuc-hanh-java-
git clone https://github.com/yourname/yourrepo.git
cd yourrepo

#Book.java
package huce.cntt.oop.th1.bai1.accessory;

public class Book {
    String title;
    String author;
    int pageNum;
    String size;
    public Book() {}
    public Book (String title, String author, int pageNum, String size) {
        this.title = title;
        this.author = author;
        this.pageNum = pageNum;
        this.size = size;
    }
    public String getTitle() {
        return title;
    }
    public String getAuthor() {
        return author;
    }
    public int getPageNum() {
        return pageNum;
    }
    public String getSize() {
        return size;
    }
    public void setTitle(String title) {
        this.title = title;
    }
    public void setAuthor(String author) {
        this.author = author;
    }
    public void setPageNum(int pageNum) {
        this.pageNum = pageNum;
    }
    public void setSize(String size) {
        this.size = size;
    }
}


#Lamp.java
package huce.cntt.oop.th1.bai1.accessory;

public class Lamp {
    float height;
    boolean status;
    String type;
    public Lamp() {}
    public Lamp(float height, boolean status, String type) {
        this.height = height;
        this.status = status;
        this.type = type;
    }
    public float getHeight() {
        return height;
    }
    public boolean isStatus() {
        return status;
    }
    public String getType() {
        return type;
    }
    public void setHeight(float height) {
        this.height = height;
    }
    public void setStatus(boolean status) {
        this.status = status;
    }
    public void setType(String type) {
        this.type = type;
    }
    public void switchLamp() {
        this.status = !status; //1 cách thông minh, làm sao để lúc bật thì tắt, lúc tắt thì bật 
    }
}


#Table.java
package huce.cntt.oop.th1.bai1.accessory;

import java.util.ArrayList;

public class Table {
    // Các thuộc tính nên để private
    private ArrayList<Book> books;
    private Lamp lamp;
    private float height;
    private float length;
    private float width;
    private String material;

    // Constructor nên để public
    public Table () {
        books = new ArrayList<>();
        lamp = new Lamp();
    }

    // Constructor thứ 2 (phương thức hàm khởi tạo)
    public Table(float height, float length, float width, String material) {
        books = new ArrayList<>();
        lamp = new Lamp();
        this.height = height;
        this.length = length;
        this.width = width;
        this.material = material;        
    }

    // Getter
    public ArrayList<Book> getBooks() {
        return books;
    }
    public Lamp getLamp() {
        return lamp;
    }    
    public float getHeight() {
        return height;
    }
    public float getLength() {
        return length;
    }
    public float getWidth() {
        return width;
    }
    public String getMaterial() {
        return material;
    }

    // Setter
    public void setBooks(ArrayList<Book> books) {
        this.books = books;
    }
    public void setLamp(Lamp lamp) {
        this.lamp = lamp;
    }
    public void setHeight(float height) {
        this.height = height;
    }
    public void setLength(float length) {
        this.length = length;
    }
    public void setWidth(float width) {
        this.width = width;
    } 
    public void setMaterial(String material) {
        this.material = material;
    }

    // Hành vi — giữ public
    public void addBook(Book b) {
        this.books.add(b);
    }
    public void display() {
        for (Book b:this.books) {
            System.out.println(b.getTitle()+" - "+b.getAuthor());
        }
    }
    public void switchLamp() {
        this.lamp.switchLamp();
    }
}

=> #App.java

package huce.cntt.oop.th1.bai1;

import huce.cntt.oop.th1.bai1.accessory.Book;
import huce.cntt.oop.th1.bai1.accessory.Lamp;
import huce.cntt.oop.th1.bai1.accessory.Table;

public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Dong oi cau lam duoc ma co lennnn nha!");
        
        Book b1 = new Book("Dung Kiem Ban Trai Trong Thung Rac", "Ky Kinh Nam Khu", 278, "16x20");
        Book b2 = new Book("Toi Phong Than Trong Tro Choi Vo Han", "Ho Ngu Lat Tieu", 589, "16x20");
        Book b3 = new Book("Thang Ngay Toi Nguy Trang Thanh NPC Trong Tro Choi Sinh Ton", "Thanh Truc Diep", 306, "16x20");
        Lamp l = new Lamp(30, false, "Den nha ma");
        Table table = new Table(80, 120, 80, "gia go");
        
        table.addBook(b1);
        table.addBook(b2);
        table.addBook(b3);
        table.setLamp(l);
        table.display();
        table.switchLamp();
    }
}











