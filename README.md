import java.util.Scanner;

public class Main{

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the number of students: ");
        int studentNum = input.nextInt();

        System.out.print("Enter " + studentNum + " scores: ");

        int scoresArray[] = new int[studentNum];
        for (int i = 0; i < studentNum; i++) {
            scoresArray[i] = input.nextInt();
        }

        int best = scoresArray[0];  // Initialize best with first score
        for (int i = 0; i < studentNum; i++) {
            if (best < scoresArray[i]) { // Find the actual best score
                best = scoresArray[i];
            }

            char letterGrade;
            if (scoresArray[i] >= (best - 10)) {
                letterGrade = 'A';
            } else if (scoresArray[i] >= (best - 20)) {
                letterGrade = 'B';
            } else if (scoresArray[i] >= (best - 30)) {
                letterGrade = 'C';
            } else if (scoresArray[i] >= (best - 40)) { // Changed to -40 for clarity
                letterGrade = 'D';
            } else {
                letterGrade = 'F';
            }

            System.out.println("Student " + i + " Score is " + scoresArray[i] + " and grade is: " + letterGrade);
        }
    }
}
