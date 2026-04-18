# MOVIE-TICKET-BOOKING-SYSTEM-BY-ARRAYLIST
This project manages movie bookings using Java ArrayList. It allows users to add movies, book tickets, view bookings, and cancel tickets. It demonstrates dynamic data handling, list operations, and OOP concepts for efficient ticket management.
# 🎬 Movie Ticket Booking System (Java - ArrayList)

## 📌 Overview

This project is a simple **Movie Ticket Booking System** built using Java.
It demonstrates how **ArrayList** can be used to dynamically store and manage multiple ticket bookings.

---

## 🎯 Objective

To design a system that:

* Displays available movies
* Books tickets for customers
* Stores booking details
* Cancels tickets
* Calculates total collection

---

## 🧠 Concepts Used

* **ArrayList (Dynamic Data Storage)**
* **Classes & Objects**
* **Loops & Conditional Statements**
* **User Input using Scanner**

---

## 🛠️ Technologies

* Java
* ArrayList (java.util)

---

## 📂 Project Structure

```id="m1t8z4"
MovieTicketSystem/
│
├── MovieTicketSystem.java   (Main File)
```

---

## 💻 Source Code

```java id="y7u2p9"
import java.util.ArrayList;
import java.util.Scanner;

class Ticket {
    String customerName;
    String movieName;
    int seatNumber;
    int price;

    Ticket(String customerName, String movieName, int seatNumber, int price) {
        this.customerName = customerName;
        this.movieName = movieName;
        this.seatNumber = seatNumber;
        this.price = price;
    }

    void display() {
        System.out.println("Customer Name : " + customerName);
        System.out.println("Movie Name : " + movieName);
        System.out.println("Seat Number : " + seatNumber);
        System.out.println("Ticket Price : ₹" + price);
        System.out.println("-----------------------------");
    }
}

public class MovieTicketSystem {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        ArrayList<Ticket> bookings = new ArrayList<>();
        int choice;

        do {
            System.out.println("\n==================================");
            System.out.println(" MOVIE TICKET SYSTEM");
            System.out.println("==================================");
            System.out.println("1. Show Movies");
            System.out.println("2. Book Ticket");
            System.out.println("3. View All Bookings");
            System.out.println("4. Cancel Ticket");
            System.out.println("5. Show Total Collection");
            System.out.println("6. Exit");
            System.out.println("==================================");
            System.out.print("Enter your choice: ");

            choice = sc.nextInt();
            sc.nextLine();

            switch (choice) {

                case 1:
                    System.out.println("\nAvailable Movies");
                    System.out.println("1. Leo");
                    System.out.println("2. Jailer");
                    System.out.println("3. Avengers");
                    System.out.println("4. Pushpa");
                    break;

                case 2:
                    System.out.println("\n===== Ticket Booking =====");

                    System.out.print("Enter Customer Name: ");
                    String name = sc.nextLine();

                    System.out.println("Select Movie");
                    System.out.println("1. Leo - ₹200");
                    System.out.println("2. Jailer - ₹180");
                    System.out.println("3. Avengers - ₹250");
                    System.out.println("4. Pushpa - ₹220");

                    System.out.print("Enter movie choice: ");
                    int movieChoice = sc.nextInt();

                    String movieName = "";
                    int price = 0;

                    switch (movieChoice) {
                        case 1:
                            movieName = "Leo";
                            price = 200;
                            break;
                        case 2:
                            movieName = "Jailer";
                            price = 180;
                            break;
                        case 3:
                            movieName = "Avengers";
                            price = 250;
                            break;
                        case 4:
                            movieName = "Pushpa";
                            price = 220;
                            break;
                        default:
                            System.out.println("Invalid movie selection");
                            continue;
                    }

                    System.out.print("Enter Seat Number: ");
                    int seat = sc.nextInt();

                    Ticket t = new Ticket(name, movieName, seat, price);
                    bookings.add(t);

                    System.out.println("\n✅ Ticket Booked Successfully!");
                    break;

                case 3:
                    System.out.println("\n===== Booking Details =====");

                    if (bookings.isEmpty()) {
                        System.out.println("No bookings found.");
                    } else {
                        for (Ticket ticket : bookings) {
                            ticket.display();
                        }
                    }
                    break;

                case 4:
                    System.out.print("\nEnter Seat Number to cancel: ");
                    int cancelSeat = sc.nextInt();
                    boolean found = false;

                    for (int i = 0; i < bookings.size(); i++) {
                        if (bookings.get(i).seatNumber == cancelSeat) {
                            bookings.remove(i);
                            found = true;
                            System.out.println(" Ticket Cancelled Successfully");
                            break;
                        }
                    }

                    if (!found) {
                        System.out.println("Seat not found!");
                    }
                    break;

                case 5:
                    int total = 0;

                    for (Ticket ticket : bookings) {
                        total += ticket.price;
                    }

                    System.out.println("\nTotal Collection: ₹" + total);
                    break;

                case 6:
                    System.out.println("Thank you for using Movie Ticket System ");
                    break;

                default:
                    System.out.println("Invalid Choice");
            }

        } while (choice != 6);

        sc.close();
    }
}
```
<img width="960" height="331" alt="1" src="https://github.com/user-attachments/assets/ae5c3697-5b9c-488b-aaaa-22cb4d85517e" />
<img width="960" height="369" alt="2" src="https://github.com/user-attachments/assets/9626be0e-663a-49d5-8358-1f31f378e2b7" />
<img width="952" height="372" alt="3" src="https://github.com/user-attachments/assets/6a10af05-fd59-4618-a2ed-296be60092a3" />
<img width="929" height="371" alt="4" src="https://github.com/user-attachments/assets/8df52ed2-4625-4663-bb6d-fb19c09bff49" />
<img width="960" height="376" alt="5" src="https://github.com/user-attachments/assets/1c8c686a-8459-4558-bd90-667f6b4323cd" />

---

## ▶️ How to Run

1. Save file as `MovieTicketSystem.java`
2. Compile:

```id="q2x8c5"
javac MovieTicketSystem.java
```

3. Run:

```id="v7n3k1"
java MovieTicketSystem
```

---

## 📥 Sample Flow

* Choose option **2** to book ticket
* Enter name → select movie → enter seat number
* Use option **3** to view bookings
* Use option **4** to cancel ticket
* Use option **5** to view total collection

---

## 🚀 Future Enhancements

* Add seat availability check
* Prevent duplicate seat booking
* Store data using database
* Add GUI using Java Swing

---

## 📌 Conclusion

This project demonstrates how **ArrayList** can be used to dynamically manage data and build a simple real-world application like a movie ticket booking system.
