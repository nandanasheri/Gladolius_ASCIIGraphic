# cs141-gladolius-ascii-graphic
Program 1 - Gladolius and ASCII Graphic in CS 141, Fall 2021 at University of Illinois at Chicago.
#include <iostream>
#include <iomanip>
/* ---------------------------------------------
Program 1: Gladiolus and ASCII Graphic

Course: CS 141, Fall 2021. Tues 10am lab
System: Windows using CLion
Author: Nandana Sheri
---------------------------------------------
*/
using namespace std;
int main() {
    int menuOption = 0;
    cout << "Program 1: Gladiolus            \n"
    << "Choose from among the following options:  \n"
    << "   1. Display original graphic  \n"
    << "   2. Display Gladiolus         \n"
    << "   3. Exit the program          \n"
    << "Your choice -> ";
    cin >> menuOption;


    //Exiting Program when Option 3 is chosen
    if (menuOption == 3) {
        exit (0);
    }

    //Displays original ASCII Graphic when Option 2 is chosen which displays the words 'MUSCAT'
    /* -------------------------------------------------------------------------------------------------
---
         ______         ____________        ______      _________     ________   _________________________
        |      \       /       |    |       |    |     /     ___|    /       |    /         \ ___    ____|
        |       \     /        |    |       |    |    /     /       /    /\__|   /     /\    \   |  |
        |     __ \___/   __    |    |       |    |   |     |___     |   /       /     /__\    \  |  |
        |    |  \       / |    |    |       |    |   \____     \    |   |    __ |    _____     | |  |
        |    |   \_____/  |    |\    \     /     /       |     |    |   |   /  ||   /      \   | |  |
        |    |            |    | \    \___/     /    ____/    /      \   \/   / |   |       |  | |  |
        |____|            |____|  \____________/     |_______/        \______/  |___|       |__| |__|

        ----------------------------------------------------------------------------------------------------*/

    else if( menuOption == 1) {
        cout << setw( 8) << " ";
        for( int i=0; i<100; i++) {
            cout << "-";
        }
        cout << endl;
        cout << setw( 8) << " " << " ______         ____________        ______      _________     ________   _________________________\n"
        << setw( 8) << " " << "|      \\       /       |    |       |    |     /     ___|    /       |    /         \\ ___    ____|\n"
        << setw( 8) << " " << "|       \\     /        |    |       |    |    /     /       /    /\\__|   /     /\\    \\   |  |\n"
        << setw( 8) << " " << "|     __ \\___/   __    |    |       |    |   |     |___     |   /       /     /__\\    \\  |  |\n"
        << setw( 8) << " " << "|    |  \\       / |    |    |       |    |   \\____     \\    |   |    __ |    _____     | |  |\n"
        << setw( 8) << " " << "|    |   \\_____/  |    |\\    \\     /     /       |     |    |   |   /  ||   /      \\   | |  |\n"
        << setw( 8) << " " << "|    |            |    | \\    \\___/     /    ____/    /      \\   \\/   / |   |       |  | |  |\n"
        << setw( 8) << " " << "|____|            |____|  \\____________/     |_______/        \\______/  |___|       |__| |__|\n"
        << endl;
        cout << setw( 8) << " ";

        for( int i=0; i<100; i++) {
            cout << "-";
        }
        cout << endl;
    }


    // Prints the Gladiolus Flower increasing in size with input taken as the Number of Sections of the Flower
    else if( menuOption == 2) {
        int numberOfSections = 0;
        cout << "Number of sections -> ";
        cin >> numberOfSections;

        //Begins by printing the top most dashes which then act as a divider between each section of the flower
        cout << setfill (' ') << setw (numberOfSections) << "" << "---";
        cout << endl;

        //Loop for managing each section of the flower
        for (int i = 0; i < numberOfSections; i++) {
            int lines = (i * 2) + 1;
            int beforeSpaces = numberOfSections - 1;
            int midSpaces = 3;

            //Loop for managing each line of each section
            for (int j = 0; j < lines; j++) {


                //This if statement prints for the top half of the flower
                if (j < (lines / 2) ) {
                    cout << setfill (' ') << setw (beforeSpaces) << "";
                    cout << '(';
                    cout << setfill (' ') << setw (midSpaces) << "";
                    cout << ')';
                    beforeSpaces--;
                    midSpaces+=2;
                }


                //This else if statement prints exclusively for the middle part along with the @ symbol
                else if (j == (lines/2) ) {
                    cout << setfill (' ') << setw (beforeSpaces) << "";
                    cout << '(';
                    cout << setfill (' ') << setw (midSpaces/2) << "";
                    cout << '@';
                    cout << setfill (' ') << setw (midSpaces/2) << "";
                    cout << ')';
                }


                // This else statement takes care of the bottom of the flower section
                else {
                    beforeSpaces++;
                    midSpaces-=2;
                    cout << setfill (' ') << setw (beforeSpaces) << "";
                    cout << '(';
                    cout << setfill (' ') << setw (midSpaces) << "";
                    cout << ')';
                }
                cout << endl;
            }
            // This cout prints the divider dashes between each section
            cout << setfill (' ') << setw (numberOfSections) << "" << "---";
            cout << endl;
        }
    //This prints the stem and the number of spaces that come before it along with the alternating stem branches
    int stem = numberOfSections * 2;
    int stemSpaces = numberOfSections + 1;

    for (int k = 0; k < stem; k++) {
        int stemSpaces = numberOfSections + 1;

        //Using the if statement the branches of the stem alternate between left and right
        if (k % 4 == 0) {
            cout << setfill (' ') << setw (stemSpaces) << "" << "|" << "/" << endl;
        }

        else if (k % 2 == 0) {
            stemSpaces = numberOfSections;
            cout << setfill (' ') << setw (stemSpaces) << "" << "\\" <<  "|" << endl;
        }

        else {
            cout << setfill (' ') << setw (stemSpaces) << "" << "|" << endl;
        }

    }
    }
    //Exiting Program after Output has been printed.
    cout << "Exiting" << endl;
    return 0;

}
