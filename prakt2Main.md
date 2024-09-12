public class Main {
    public static void main(String[] args) {
        Car_1 uazic_0 = new Car_1();
        Car_1 uazic_1 = new Car_1("uaz-52", "yes", "white", 2026);
        

        To_String(uazic_1);

        System.out.print('\n');

        uazic_0.setColor("yellow");
        uazic_0.setLicense("no");
        uazic_0.setModel("gaz-69");
        uazic_0.setYear(2029);

        System.out.print("Model: " + uazic_0.getModel());
        System.out.print("\nLicense: " + uazic_0.getLicense());
        System.out.print("\nColor: " + uazic_0.getColor());
        System.out.print("\nYear: " + uazic_0.getYear());
        System.out.print("\nAge of the car: " + uazic_0.carAge());
    }
    public static void To_String (Car_1 car) {
        System.out.print("Model: " + car.model + "\nLicense: " + car.license + "\nColor: " + car.color + "\nYear: "
                + car.year + '\n');
    }
}
