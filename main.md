import java.util.Scanner;

// Kenyah Collins, 2/5/2023, This program calculates a users bmi based on input of their weight and height
public class Main {
    private static Scanner input = new Scanner(System.in);

    public static void main(String[] args) {
        double lbs, inches, meters, kgs, bmi;
        String classification;
        //title
        System.out.println();
        System.out.println("\tBMI Calculator");
        System.out.println();

        //user input
        System.out.print("Please Enter weight (lbs): ");
        lbs = input.nextDouble();
        System.out.print("Please enter height (inches): ");
        inches = input.nextDouble();
        System.out.println();

        //output to user
        meters = convertToMeters(inches);
        kgs = convertToKilograms(lbs);
        bmi = calcBMI(kgs, meters);
        System.out.println("Your BMI is " + calcBMI(kgs, meters));
        System.out.println("Your BMI classification is " + bmiClassification(bmi));
    }

    //methods
    // convert pounds to kilograms
    public static double convertToKilograms(double lbs) {
        double kgs = lbs / 2.2046;
        return kgs;
    }

    // convert inches to meters
    public static double convertToMeters(double inches) {
        double meters = inches / 39.37;
        return meters;
    }

    // take weight in kilograms and height in meters and return the BMI
    public static double calcBMI(double kgs, double meters) {
        double bmi = kgs / meters;
        return bmi;
    }

    // take the value for the BMI and return a String with the BMI classification
    public static String bmiClassification(double bmi) {
        String classification;

        if (bmi < 18.5)
            classification = "underweight";
        else if (bmi < 25.0)
            classification = "normal weight";
        else if (bmi < 30.0)
            classification = "overweight";
        else
            classification = "obese";
        return classification;
    }
}
