import java.util.Scanner;

public class Main {

    public static double add(double a, double b) {
        return a + b;
    }

    public static double subtract(double a, double b) {
        return a - b;
    }

    public static double multiply(double a, double b) {
        return a * b;
    }

    public static double divide(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Cannot divide by zero!");
            return 0;
        }
        return a / b;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        char again;

        do {
            System.out.println("Select operation: + for Add, - for Subtract, * for Multiply, / for Divide");
            char op = scanner.next().charAt(0);

            System.out.print("Enter first number: ");
            double firstNumber = scanner.nextDouble();

            System.out.print("Enter second number: ");
            double secondNumber = scanner.nextDouble();

            double result = 0;

            switch (op) {
                case '+':
                    result = add(firstNumber, secondNumber);
                    break;
                case '-':
                    result = subtract(firstNumber, secondNumber);
                    break;
                case '*':
                    result = multiply(firstNumber, secondNumber);
                    break;
                case '/':
                    result = divide(firstNumber, secondNumber);
                    break;
                default:
                    System.out.println("Invalid operation!");
            }

            System.out.println("Result: " + result);

            System.out.print("Do you want to calculate again? (y/n): ");
            again = scanner.next().charAt(0);

        } while (again == 'y' || again == 'Y');

        scanner.close();
        System.out.println("Thanks for using MyConsoleCalc! Bye :)");
    }
}

