## Задача 1 ##
### Напишите программу, которая конвертирует сумму денег из китайских юаней в российские рубли по курсу покупки 11.91. ###
```java
import java.util.Scanner;
public class main {
    public static void main(String[] args){
        final double ROUBLES_PER_YUAN = 11.91;
        int yuan;
        Scanner input = new Scanner(System.in);
        System.out.print("Введите сумму в юанях: ");
        yuan = input.nextInt();
        if (yuan<=0)
            System.out.println("Введено неверное значение, количество юаней положительное число");
        else {
            double roubles;
            System.out.println("Сумма в рублях состовляет: " + roubles);
        }
    }
}


