# Интерфейс BikeParts.java

```
package app;

public interface BikeParts {
    String getManufacturer();
    void setManufacturer(String manufacturer);
}
```
# Интерфейс MountainParts.java

```
package app;

public interface MountainParts {
    String TERRAIN = "off_road";

    void setSuspension(String newValue);
    String getSuspension();

    void setType(String newValue);
    String getType();
}
```
# Интерфейс RoadParts.java

```
package app;

public interface RoadParts {
    String TERRAIN = "track_racing";

    void setTyreWidth(int newValue);
    int getTyreWidth();

    void setPostHeight(int newValue);
    int getPostHeight();
}
```

# Класс Bike.Java
```
package app;

public class Bike implements BikeParts {
    private String handleBars, frame, types, seatType;
    public int numGears;
    private final String make;

    public Bike() {
        this.make = "Oracle Cycles";
    }

    public Bike(String handleBars, String frame, String types, String seatType, int numGears) {
        this.handleBars = handleBars;
        this.frame = frame;
        this.types = types;
        this.seatType = seatType;
        this.numGears = numGears;
        this.make = "Oracle Cycles";
    }

    @Override
    public String getManufacturer() {
        return make;
    }

    @Override
    public void setManufacturer(String manufacturer) {
        // Неизменяемое значение
    }

    protected void printDescription() {
        System.out.println("\n" + this.make + "\n" +
                "This bike has " + this.handleBars + " handlebars on a " +
                this.frame + " frame with " + this.numGears + " gears." +
                "\nIt has a " + this.seatType + " seat with " + this.types + " tyres.");
    }
}
```
# Класс RoadBike.java

```
package app;

public class RoadBike extends Bike implements RoadParts {
    private int tyreWidth, postHeight;

    public RoadBike() {
        this("drop", "racing", "tread less", "razor", 20, 22); // Указываем только необходимые параметры
    }

    public RoadBike(String handleBars, String frame, String types, String seatType,
                    int tyreWidth, int postHeight) {
        super(handleBars, frame, types, seatType, 18); // Укажите значение numGears здесь
        this.tyreWidth = tyreWidth;
        this.postHeight = postHeight;
    }

    @Override
    public void setTyreWidth(int newValue) {
        this.tyreWidth = newValue;
    }

    @Override
    public int getTyreWidth() {
        return tyreWidth;
    }

    @Override
    public void setPostHeight(int newValue) {
        this.postHeight = newValue;
    }

    @Override
    public int getPostHeight() {
        return postHeight;
    }

    public void printDescription() {
        super.printDescription();
        System.out.println("This Roadbike has " + this.tyreWidth + " mm tyres and a post height of " + this.postHeight + ".");
    }
}
```

# Класс BikeDriver.java

```
package app;

public class BikeDriver {
    public static void main(String[] args) {
        MountainBike mountainBike = new MountainBike("Bull Horn", "Hardtail", "Maxxis", "dropper", "Air", "Trail", 19);
        mountainBike.printDescription();
    }
}
```

# Класс MountainBike.java 

```
package app;

public class MountainBike extends Bike implements MountainParts {
    private String suspension, type;
    private int frameSize;

    // Конструктор по умолчанию
    public MountainBike() {
        this("Bull Horn", "Hardtail", "Maxxis", "dropper", "Air", "Trail", 19);
    }

    // Основной конструктор
    public MountainBike(String handleBars, String frame, String types, String seatType,
                        String suspension, String type, int frameSize) {
        super(handleBars, frame, types, seatType, 18); // Передаем значение numGears
        this.suspension = suspension;
        this.type = type;
        this.frameSize = frameSize;
    }

    @Override
    public void setSuspension(String newValue) {
        this.suspension = newValue;
    }

    @Override
    public String getSuspension() {
        return suspension;
    }

    @Override
    public void setType(String newValue) {
        this.type = newValue;
    }

    @Override
    public String getType() {
        return type;
    }

    public void printDescription() {
        super.printDescription();
        System.out.println("This mountain bike is a " + this.type + " bike and has a " + this.suspension + " suspension.");
    }
}
```
