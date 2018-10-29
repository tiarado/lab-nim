# lab-nim
import java.util.Scanner;
public class Nim {
    //main method
    public static void main() 
    {
        Scanner in = new Scanner(System.in);
        //two players can play this game
        System.out.println("Player 1, Enter your name: ");
        String first = in.nextLine();
        System.out.println("Player 2, Enter your name: ");
        String second = in.nextLine();
        
        //Allows the players to customize how many sticks to start with
        System.out.println("How many sticks would you like to start with?");
        int sticks = in.nextInt();
        //keeps track of whose turn it is
        int turnCount = 0;
        
        //a while loop keeps executing this code until there are no more sticks 
        while (sticks > 0) {
            printSticks(sticks);
            System.out.println();
            System.out.println("Would you like to remove 1 or 2 sticks?");
            int n = in.nextInt();
            
            //a conditional statement makes sure that only 1 or 2 sticks can be removed
            if(n==1){
                System.out.print("1 stick removed");
                sticks--;
                System.out.println();
                turnCount++;
            }
            else if(n==2){
                System.out.print("2 sticks removed");
                sticks = sticks-2;
                System.out.println();
                turnCount++;
            }
            //if the user types anything else, it will ask the user again
            else{
                System.out.print("You can only remove 1 or 2 sticks.");
                System.out.println();
            }
        }
        
         //turnCount keeps track of which player wins
        if(turnCount % 2 == 1){
            System.out.println(second + " wins!");
        }
        else if(turnCount % 2 ==0){
            System.out.println(first + " wins!");
        }
    }
    
    //method for printing sticks  
    public static void printSticks(int sticks) {
        for (int i = 0; i < sticks; i++) {
            System.out.print("|");
        }
    }
    }
    
