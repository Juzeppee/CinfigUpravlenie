*Car.java*

```
package vehicles;

public class car extends vehicle {
    public car(String model, String licence, String color, int year,
               String ownerName, String insuranceNumber, String engineType) {
        super(model, licence, color, year, ownerName, insuranceNumber, engineType);
        this.engineType = "Бензиновый";
    }

    @Override
    public String vehicle_type() {
        return "Машина";
    }

    @Override
    public String to_string() {
        return super.to_string() + " engine type - " + engineType;
    }
}

```

*electric_car.java*

```
package vehicles;

public class electric_car extends car implements electric_vehicle {
    private int batteryCapacity;

    public electric_car(String model, String licence, String color, int year,
                        String ownerName, String insuranceNumber, String engineType, int batteryCapacity) {
        super(model, licence, color, year, ownerName, insuranceNumber, "Электрический");
        this.batteryCapacity = batteryCapacity;
    }

    public int get_batteryCapacity() {
        return batteryCapacity;
    }

    public void set_batteryCapacity(int batteryCapacity) {
        this.batteryCapacity = batteryCapacity;
    }

    @Override
    public String to_string() {
        return super.to_string() + " заряд батареи - " + batteryCapacity;
    }

    @Override
    public String vehicle_type() {
        return "Электрическая машина";
    }
}
```

*vehicle.java*

```
package vehicles;

public abstract class vehicle {
    private String model;
    private String licence;
    private String color;
    private int year;
    private String ownerName;
    private String insuranceNumber;
    protected String engineType;

    public vehicle(String model, String licence, String color, int year,
                   String ownerName, String insuranceNumber, String engineType) {
        this.model = model;
        this.licence = licence;
        this.color = color;
        this.year = year;
        this.ownerName = ownerName;
        this.insuranceNumber = insuranceNumber;
        this.engineType = engineType;
    }

    public String get_model() {
        return model;
    }

    public void set_model(String model) {
        this.model = model;
    }

    public String get_licence() {
        return licence;
    }

    public void set_licence(String licence) {
        this.licence = licence;
    }

    public String get_color() {
        return color;
    }

    public void set_color(String color) {
        this.color = color;
    }

    public int get_year() {
        return year;
    }

    public void set_year(int year) {
        this.year = year;
    }

    public String get_ownerName() {
        return ownerName;
    }

    public void set_ownerName(String ownerName) {
        this.ownerName = ownerName;
    }

    public String get_insuranceNumber() {
        return insuranceNumber;
    }

    public void set_insuranceNumber(String insuranceNumber) {
        this.insuranceNumber = insuranceNumber;
    }

    public String get_engineType() {
        return engineType;
    }

    public void set_engineType(String engineType) {
        this.engineType = engineType;
    }

    public abstract String vehicle_type();

    public String to_string() {
        return " Вид транспорта - " + vehicle_type() +
                " модель - " + model +
                "  номерной знак - " + licence +
                "  цвет - " + color +
                "  год выпуска - " + year +
                " Владелец - " + ownerName +
                " номер страховки - " + insuranceNumber;
    }
}
```

*electric_vehicle.java*

```
package vehicles;

public interface electric_vehicle {
    int get_batteryCapacity();
    void set_batteryCapacity(int batteryCapacity);
}

```
*test_car.java*
```

package app;

import vehicles.car;
import vehicles.electric_car;
import vehicles.vehicle;

public class test_car {
    public static void main(String[] args) {
        car car = new car("Polo Sedan", "E101KB", "Red", 2018, "Stasyan Letyagin", "55123", "Бензиновый");
        electric_car electriccar = new electric_car("Volkswagen", "C211MK", "Blue", 2024, "Ivanov Ivan", "65134", "Электрический", 52);

        car.set_year(2022);
        car.set_ownerName("Stasyan Letyagin");
        car.set_insuranceNumber("693901");

        System.out.println(car.to_string());
        System.out.println(electriccar.to_string());
        System.out.println(electriccar.get_batteryCapacity());
    }
}
```
