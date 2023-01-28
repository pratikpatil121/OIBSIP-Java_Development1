import java.util.Random;
import java.util.Scanner;

class game {
    Random rand = new Random();
    private int compno, inp;
    private int noOf = 10;

    public game() {
        compno = rand.nextInt(100);
    }

    public void takeUserInput(int inpu) {
        this.inp = inpu;
    }

    public String iscorrectnumber() {
        return "your choice is correct";
    }

    public void noOfguesses() {

        if (inp == compno) {
            System.out.println(iscorrectnumber());
            System.out.printf("Score is:%d", noOf);
        } else if (inp > compno) {
            System.out.println("Your guess is greater than expected No");
            System.out.printf("chances left:%d", noOf - 1);
        } else {
            System.out.println("Your guess is less than expected no.");
            System.out.printf("Score is:%d", noOf - 1);
        }

    }

}

public class Guess_Game {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        game g = new game();
        System.out.println("lets play a game ,  GUESS THE NUMBER");
        System.out.println("you will get 10 chances to guess the number ");
        for (int i = 0; i < 10; i++) {
            int choice = sc.nextInt();
            g.takeUserInput(choice);
            g.noOfguesses();

        }
    }

}
