## Задача 1 ##
### Напишите программу, которая конвертирует сумму денег из китайских юаней в российские рубли по курсу покупки 11.91. ###
import java.util.Scanner; <br>
public class main {<br>
    <br>public static void main(String[] args){<br>
        <br>final double ROUBLES_PER_YUAN = 11.91;<br>
        <br>int yuan;<br>
        <br>Scanner input = new Scanner(System.in);<br>
        <br>System.out.print("Введите сумму в юанях: ");<br>
        <br>yuan = input.nextInt();<br>
        <br>if (yuan<=0)<br>
            <br>System.out.println("Введено неверное значение, количество юаней положительное число");<br>
        <br>else {<br>
            <br>double roubles;<br>
            <br>System.out.println("Сумма в рублях состовляет: " + roubles);<br>
        <br>}
    <br>}
<br>}


## Задача 2 ##
### Перепишите программу, которая конвертирует сумму денег из китайских юаней в российские рубли по курсу покупки 11.91, добавив структуру выбора для принятия решений об окончаниях входной валюты в зависимости от ее значения. ### 
import java.util.Scanner;
public class ConvectYuan {
    public static void main(String[] args){
        final double ROUBLES_PER_YUAN = 11.91;
        int yuan, digit, digit2;
        Scanner input = new Scanner(System.in);
        System.out.print("Введите сумму денег в юянях: ");
        yuan = input.nextInt();
        if (yuan <= 0)
            System.out.println("Введено неверное значение, значение должно быть полож.");
        else {
            digit = yuan % 10;
            digit2 = (yuan / 10) %10;
            if (digit == 1 && digit2 != 1)
                System.out.println("Был введен " + yuan + " юань.");
            else if (digit > 1 && digit < 5 && digit2 !=1) {
                System.out.println("Было Введено " + yuan + " юаня.");
            } else
                System.out.println("Было введено " + yuan + " юаней.");
            double roubles;
            roubles = ROUBLES_PER_YUAN * yuan;
            System.out.println("Сумма денег в рублях составляет " + roubles);
        }
    }
}<br>
