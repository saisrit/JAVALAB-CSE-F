```
import java.util.*;

class Cricket {
    String playerName;
    String teamName;
    double battingAverage;

    // Constructor
    Cricket(String playerName, String teamName, double battingAverage) {
        this.playerName = playerName;
        this.teamName = teamName;
        this.battingAverage = battingAverage;
    }

    // Method to display player details
    void display() {
        System.out.println("Player: " + playerName + ", Batting Average: " + battingAverage);
    }
}

public class CricketTeam {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Number of players: ");
        int n = sc.nextInt();
        sc.nextLine();

        Cricket[] players = new Cricket[n];

        // Reading player details
        for (int i = 0; i < n; i++) {
            System.out.println("Enter details for Player " + (i + 1));

            System.out.print("Name: ");
            String name = sc.nextLine();

            System.out.print("Team: ");
            String team = sc.nextLine();

            System.out.print("Batting Average: ");
            double avg = sc.nextDouble();
            sc.nextLine();

            players[i] = new Cricket(name, team, avg);
        }

        // Display team-wise players
        boolean[] printed = new boolean[n];

        for (int i = 0; i < n; i++) {
            if (!printed[i]) {
                String team = players[i].teamName;
                System.out.println("\nTeam: " + team);

                for (int j = 0; j < n; j++) {
                    if (players[j].teamName.equals(team)) {
                        players[j].display();
                        printed[j] = true;
                    }
                }
            }
        }

        sc.close();
    }
}
```
