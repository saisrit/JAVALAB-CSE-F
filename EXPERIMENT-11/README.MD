```
class Reservation {
    int availableBerths;

    Reservation(int berths) {
        availableBerths = berths;
    }

    synchronized void reserve(String name, int requestedBerths) {
        System.out.println(name + " requesting " + requestedBerths + " berths");

        if (requestedBerths <= availableBerths) {
            System.out.println("Berth confirmed for " + name);
            availableBerths = availableBerths - requestedBerths;
            System.out.println("Ticket printed for " + name);
        } else {
            System.out.println("No berths available for " + name);
        }

        System.out.println("Available Berths: " + availableBerths);
        System.out.println("---------------------------");
    }
}

class Person extends Thread {
    Reservation reservation;
    int berths;

    Person(Reservation reservation, String name, int berths) {
        super(name);
        this.reservation = reservation;
        this.berths = berths;
    }

    public void run() {
        reservation.reserve(getName(), berths);
    }
}

public class TrainReservation {
    public static void main(String[] args) {

        Reservation r = new Reservation(5);

        Person p1 = new Person(r, "RAJU", 2);
        Person p2 = new Person(r, "SAI", 1);
        Person p3 = new Person(r, "RAMU", 3);
        Person p4 = new Person(r, "BOBY", 1);

        p1.start();
        p2.start();
        p3.start();
        p4.start();
    }
}


```

