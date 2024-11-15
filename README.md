# Labtask2
import java.io.File;
import java.io.PrintWriter;
import java.util.Scanner;

public class ReadFile {
    public static void main(String[] args) {
        try {
            File inFile = new File("Input.txt");
            Scanner in = new Scanner(inFile);
            PrintWriter out = new PrintWriter(new File("Output2.txt"));

            if (in.hasNextLine()) {
                String line = in.nextLine();
                String[] nums = line.split(",");
                for (int i = 0; i < nums.length; i++) {
                    int n = Integer.parseInt(nums[i]);
                    int sum = (n * (n + 1)) / 2;
                    out.print(sum);
                    if (i != nums.length - 1) {
                        out.print(", ");
                    }
                }
            }

            in.close();
            out.close();
            System.out.println("File written successfully.");
        } catch (Exception e) {
            System.out.println("File not found.");
        }
    }
}
