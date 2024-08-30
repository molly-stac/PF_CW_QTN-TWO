#include <iostream>

void printDivisors(int n)
{
    std::cout << "The divisors of " << n << " are:" << std::endl;
    for (int i = n; i >= 1; i--)
    {
        if (n % i == 0)
        {
            std::cout << i << std::endl;
        }
    }
}

int main()
{
    // Our First Alerts when the Programs Runs First

    std::cout << "This program is designed to exhibit the positive divisors of positive integers supplied by you.\n" << std::endl;
    std::cout << "The program will repeatedly prompt you to enter a positive integer.\n" << std::endl;
    std::cout << "Each time you enter a positive integer, the program will print all the divisors of your integer in a column and in decreasing order.\n" << std::endl;
    std::cout << "You can terminate the program by entering a negative integer or zero." << std::endl;

    char response;
    int num; 

    do
    {
        std::cout << "Please enter a positive integer (or 0 or negative to quit): ";
        std::cin >> num;

        if (num <= 0)
        {
            std::cout << "You entered a non-positive integer. The program will now terminate." << std::endl;
            break;
        }

        printDivisors(num);

        std::cout << "Would you like to see the divisors of another integer (Y/N)? ";
        std::cin >> response;

        while (response !=  'Y' &&  response != 'y' && response != 'N' && response != 'n')
        {
            std::cout << "Please respond with Y (or y) for yes and N (or n) for no." << std::endl;
            std::cout << "Would you like to see the divisors of another integer (Y/N)? ";
            std::cin >> response;
        }

    } while (response == 'Y' ||  response == 'y');

    return 0;
}
