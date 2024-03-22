import java.util.Scanner;
import java.util.Random;

class Guess {
    public static void main (String[] args) {
        Scanner reader = new Scanner(System.in);
        String play = "yes";

        while (play.equals("yes")) {
            Random rand = new Random();
            int randNum = rand.nextInt(100);
            int guess = -1;
            int tries = 0;

            while (guess != randNum) {
                System.out.print("GUESSING NUMBER BETWEEN 1 AND 100: ");
                guess = reader.nextInt();
                tries++;

                if (guess == randNum) {
                    System.out.println("AWESOME YOU GUESSED THE NUMBER!");
                    System.out.println("IT ONLY TOOK YOU " + tries + " guesses!");
                    System.out.print("WOULD YOU LIKE TO PLAY AGAIN? Yes or No: ");
                    play = reader.next().toLowerCase();
                } else if (guess > randNum) {
                    System.out.println("YOUR GUESS IS TOO HIGH, TRY AGAIN");
                } else {
                    System.out.println("YOUR GUESS IS TOO LOW");
                }
            }
        }
        reader.close();
    }
}
