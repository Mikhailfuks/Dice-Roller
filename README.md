using System;

public class DiceRoller
{
    public static void Main(string[] args)
    {
        int numDice, numSides;

        //Input with error handling
        while (true)
        {
          Console.Write("Enter the number of dice (must be > 0): ");
          if (int.TryParse(Console.ReadLine(), out numDice) && numDice > 0)
          {
              break;
          }
          Console.WriteLine("Invalid input. Please enter a positive integer.");
        }
        while (true)
        {
          Console.Write("Enter the number of sides on each die (must be > 0): ");
          if (int.TryParse(Console.ReadLine(), out numSides) && numSides > 0)
          {
              break;
          }
          Console.WriteLine("Invalid input. Please enter a positive integer.");
        }

        Random random = new Random();
        int total = 0;
        Console.Write("Your rolls: ");
        for (int i = 0; i < numDice; i++)
        {
            int roll = random.Next(1, numSides + 1);
            Console.Write($"{roll} ");
            total += roll;
        }
        Console.WriteLine($"\nTotal: {total}");
    }
}
