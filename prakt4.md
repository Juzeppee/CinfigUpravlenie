*TestCar.java*
```
package app;
import vehicles.Car;
import vehicles.ElectricCar;
import vehicles.Vehicle;

public class TestCar {
    public static void main(String[] args) {
        Vehicle car = new Car("kia rio", "В004КО", "white", "2012", "Арген Марянович Оглы", "INS22833");
        Vehicle electricCar = new ElectricCar("TESLA CUBERTRUCK", "М101АМ", "Black", "2023", "Варпач", "INS67890", "75%");
        car.setColor("Yellow");
        ((ElectricCar) electricCar).setBatteryCapacity("100%");

  System.out.println("---Машина---");
  car.toString();
  System.out.println("---Электро Машина---");
  electricCar.toString();
    }
}
```


*ElectricCar.java*
```
package vehicles;
import vehicles.Vehicle;

public class ElectricCar extends Car {
    private String batteryCapacity;

    public ElectricCar(String model, String license, String color, String year, String ownerName, String insuranceNumber, String batteryCapacity) {
        super(model, license, color, year, ownerName, insuranceNumber);
        this.batteryCapacity = batteryCapacity;
        this.engineType = "Electric engine";
    }

    public String getBatteryCapacity() {
        return batteryCapacity;
    }

    public void setBatteryCapacity(String batteryCapacity) {
        this.batteryCapacity = batteryCapacity;
    }

    @Override
    public String vehicleType() {
        return "Electric Car";
    }

    public String toString(){
        super.toString();
        System.out.println(this.batteryCapacity);
        return null;
    }
} ```
```
*Car.java
```
package vehicles;
import vehicles.Vehicle;

public class Car extends Vehicle {

    public Car(String model, String license, String color, String year, String ownerName, String insuranceNumber) {
        super(model, license, color, year, ownerName, insuranceNumber);
        this.engineType = "Petrol engine";
    }

    @Override
    public String vehicleType() {
        return "Car";
    }
}
```

*Vehicle.java*
```
package vehicles;
public abstract class Vehicle
{
private String model;
private String license;
private String color;
private String year;
private String ownerName;
private String insuranceNumber;
protected String engineType;

public Vehicle(String model, String license, String color, String year, String ownerName, String insuranceNumber) {
    this.model = model;
    this.license = license;
    this.color = color;
    this.year = year;
    this.ownerName = ownerName;
    this.insuranceNumber = insuranceNumber;
}

public String getModel() {
    return model;
}

public void setModel(String model) {
    this.model = model;
}

public String getLicense() {
    return license;
}

public void setLicense(String license) {
    this.license = license;
}

public String getColor() {
    return color;
}

public void setColor(String color) {
    this.color = color;
}

public String getYear() {
    return year;
}

public void setYear(String year) {
    this.year = year;
}

public String getOwnerName() {
    return ownerName;
}

public void setOwnerName(String ownerName) {
    this.ownerName = ownerName;
}

public String getInsuranceNumber() {
    return insuranceNumber;
}

public void setInsuranceNumber(String insuranceNumber) {
    this.insuranceNumber = insuranceNumber;
}

public abstract String vehicleType();

@Override
public String toString(){
    System.out.println(this.model);
    System.out.println(this.year);
    System.out.println(this.license);
    System.out.println(this.color);
    System.out.println(this.ownerName);
    System.out.println(this.insuranceNumber);
    System.out.println(this.engineType);
    return null;
}


}
```
