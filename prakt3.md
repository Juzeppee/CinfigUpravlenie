*Main.java*
```
package app;
import vehicles.Car;
import vehicles.ElectricCar;

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Стасянчик", "123456", "Бензиновый");
        ElectricCar myElectricCar = new ElectricCar("Гошанчик", "654321", "Электрический", 100);

System.out.println("Владелец машины: " + myCar.getOwnerName());
System.out.println("Номер страховки: " + myCar.getInsuranceNumber());
System.out.println("Тип двигателя: " + myCar.getEngineType());
System.out.println("Владелец электрической машины: " + myElectricCar.getOwnerName());
System.out.println("Номер страховки электрической машины: " + myElectricCar.getInsuranceNumber());
System.out.println("Тип двигателя: " + myElectricCar.getEngineType());
System.out.println("Остаток зарядки: " + myElectricCar.getBatteryCapacity());
    }
}
```

*ElectricCar.java*
```
package vehicles;

public class ElectricCar extends Car {
    private int batteryCapacity;

    public ElectricCar(String ownerName, String insuranceNumber, String engineType, int batteryCapacity) {
        super(ownerName, insuranceNumber, engineType);
        this.batteryCapacity = batteryCapacity;
    }

    public int getBatteryCapacity() {
        return batteryCapacity;
    }

    public void setBatteryCapacity(int batteryCapacity) {
        this.batteryCapacity = batteryCapacity;
    }
}
```

*Car.java*
```
package vehicles;

public class Car {
    private String ownerName;
    private String insuranceNumber;
    protected String engineType;

    public Car(String ownerName, String insuranceNumber, String engineType) {
        this.ownerName = ownerName;
        this.insuranceNumber = insuranceNumber;
        this.engineType = engineType;
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


    public String getEngineType() {
        return engineType;
    }

    public void setEngineType(String engineType) {
        this.engineType = engineType;
    }
}

