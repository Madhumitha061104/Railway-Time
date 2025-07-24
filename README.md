import java.util.Scanner;
import java.text.SimpleDateFormat;
import java.util.Date;

public class RailwayTime {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user for input
        System.out.print("Enter time in 12-hour format (hh:mm a): ");
        String inputTime = scanner.nextLine();

        try {
            // Define 12-hour format
            SimpleDateFormat twelveHourFormat = new SimpleDateFormat("hh:mm a");
            // Define 24-hour format
            SimpleDateFormat twentyFourHourFormat = new SimpleDateFormat("HH:mm");

            // Parse input time
            Date date = twelveHourFormat.parse(inputTime);
            // Format to 24-hour time
            String railwayTime = twentyFourHourFormat.format(date);

            System.out.println("Railway (24-hour) time: " + railwayTime);

        } catch (Exception e) {
            System.out.println("Invalid input format. Please use hh:mm AM/PM format.");
        }

        scanner.close();
    }
}
