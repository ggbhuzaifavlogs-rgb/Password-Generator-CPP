[Pasword Generator.cpp](https://github.com/user-attachments/files/32290403/Pasword.Generator.cpp)
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

using namespace std;

int main()
{
    srand(time(0));

    cout << "========================================" << endl;
    cout << "        PASSWORD GENERATOR" << endl;
    cout << "========================================" << endl;
    cout << endl;

    cout << "1. Generate Password" << endl;
    cout << "2. Exit" << endl;
    cout << endl;

    int choice;

    cout << "Choose an option: ";
    cin >> choice;

    if (choice == 1)
    {
        int length;

        cout << endl;
        cout << "Enter password length: ";
        cin >> length;

        string characters =
            "abcdefghijklmnopqrstuvwxyz"
            "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
            "0123456789"
            "!@#$%^&*";

        string password = "";

        for (int i = 0; i < length; i++)
        {
            int randomIndex = rand() % characters.length();

            password += characters[randomIndex];
        }

        cout << endl;
        cout << "Generated Password: " << password << endl;

        if (length < 8)
        {
            cout << "Strength: WEAK" << endl;
        }
        else if (length < 12)
        {
            cout << "Strength: MEDIUM" << endl;
        }
        else
        {
            cout << "Strength: STRONG" << endl;
        }
    }
    else if (choice == 2)
    {
        cout << endl;
        cout << "Thank you for using Password Generator!" << endl;
    }
    else
    {
        cout << endl;
        cout << "Invalid option." << endl;
    }

    return 0;
}
