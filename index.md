## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/alfredogomez2005/alfredogomez.github.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Enhancement Aritifact

For my enhancement in Category One: Software Engineering/Design, I chose to work on a project called Buffer Overflow. When I initially ran the code, it would not cause the buffer to overflow. I could not figure out what the issues were. See code below:

// BufferOverflow.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include <iomanip>
#include <iostream>
#include <string>

int main()
{
  std::cout << "Buffer Overflow Example" << std::endl;

  // TODO: The user can type more than 20 characters and overflow the buffer, resulting in account_number being replaced -
//  even though it is a constant and the compiler buffer overflow checks are on.
//  You need to modify this method to prevent buffer overflow without changing the account_number
//  varaible, and its position in the declaration. It must always be directly before the variable used for input.

  const std::string account_number = "CharlieBrown42";
  char user_input[20];
  std::cout << "Enter a value: ";

  //LIMIT SIZE OF VARIABLE INPUT TO PREVENT BUFFER OVERFLOW

  std::cout << "You entered: " << user_input << std::endl;
  std::cout << "Account Number = " << account_number << std::endl;
}

// Run program: Ctrl + F5 or Debug > Start Without Debugging menu
// Debug program: F5 or Debug > Start Debugging menu
  
![CS 405 Buffer Overflow Debug](https://user-images.githubusercontent.com/79815877/172033460-b2fd6647-3391-4b5b-bf37-496812ecfd58.jpg)

As you can see if you run the code, it does not output correctly. My enhancement for this specific project is to figure out what the solution is and execute the code correctly. Something is either written incorrectly or I'm missing something. 
  
  *UPDATE*

I figured out what the issue was. The code was missing the line of code to limit the size of the variable. See below:
  
// BufferOverflow.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include <iomanip>
#include <iostream>
#include <string>

int main()
{
  std::cout << "Buffer Overflow Example" << std::endl;

  // TODO: The user can type more than 20 characters and overflow the buffer, resulting in account_number being replaced -
//  even though it is a constant and the compiler buffer overflow checks are on.
//  You need to modify this method to prevent buffer overflow without changing the account_number
//  varaible, and its position in the declaration. It must always be directly before the variable used for input.

  const std::string account_number = "CharlieBrown42";
  char user_input[20];
  std::cout << "Enter a value: ";

  //LIMIT SIZE OF VARIABLE INPUT TO PREVENT BUFFER OVERFLOW
  std::cin >> std::setw(20) >> user_input;     //This was the missing line of code. When I ran the debugger before, it would not allow me to input any data.

  std::cout << "You entered: " << user_input << std::endl;
  std::cout << "Account Number = " << account_number << std::endl;
}

// Run program: Ctrl + F5 or Debug > Start Without Debugging menu
// Debug program: F5 or Debug > Start Debugging menu

![CS 405 Buffer Overflow Debug Correction](https://user-images.githubusercontent.com/79815877/172033475-d22cd82c-57e4-4ed5-be5f-1500012e8d84.jpg)


For my enhancement in Category Two: Algorithms and Data Structures, I chose to work on a project called Lab 1-3. This specific project creates a menu with 3 different selctions. The code is not finished and I had to figure out what to input as the type and variable. When I intially did the project, I had no idea what they meant by types and variables. See below:
  
//============================================================================
// Name        : Lab1-3.cpp
// Author      : your name
// Version     : 1.0
// Copyright   : Copyright © 2017 SNHU COCE
// Description : Lab 1-3 Up to Speed in C++
//============================================================================

#include <algorithm>
#include <iostream>

using namespace std;

//============================================================================
// Global definitions visible to all methods and classes
//============================================================================

// FIXME (1): Define a data structure to hold bid information together as a single unit of storage.
?type?

// FIXME (4): Display the bid values passed in data structure
/**
 * Display the bid information
 *
 * @param ?type? data structure containing the bid info
 */
void displayBid(?type? ?variable?) {
    cout << "Title: " << ?variable?.Title << endl;
    cout << "Fund: " << ?variable?.Fund << endl;
    cout << "Vehicle: " << ?variable?.Vehicle << endl;
    cout << "Bid Amount: " << ?variable?.amount << endl;

    return;
}

// FIXME (3): Store input values in data structure
/**
 * Prompt user for bid information
 *
 * @return data structure containing the bid info
 */
?type? ?variable?() {
    ?type? ?variable?

    cin.ignore();
    cout << "Enter title: ";
    getline(cin, ?variable?.Title);

    cout << "Enter fund: ";
    cin >> ?variable?.Fund;

    cin.ignore();
    cout << "Enter vehicle: ";
    getline(cin, ?variable?.Vehicle);

    cin.ignore();
    cout << "Enter amount: ";
    string strAmount;
    getline(cin, strAmount);
    ?variable?.amount = strToDouble(strAmount, '$');

    return ?variable?
}

/**
 * Simple C function to convert a string to a double
 * after stripping out unwanted char
 *
 * credit: http://stackoverflow.com/a/24875936
 *
 * @param ch The character to strip out
 */
double strToDouble(string str, char ch) {
    str.erase(remove(str.begin(), str.end(), ch), str.end());
    return atof(str.c_str());
}


/**
 * The one and only main() method
 */
int main() {

    // FIXME (2): Declare instance of data structure to hold bid information
    ?type? ?variable?

    // loop to display menu until exit chosen
    int choice = 0;
    while (choice != 9) {
        cout << "Menu:" << endl;
        cout << "  1. Enter Bid" << endl;
        cout << "  2. Display Bid" << endl;
        cout << "  9. Exit" << endl;
        cout << "Enter choice: ";
        cin >> choice;

        // FIXME (5): Complete the method calls then test the program
        switch (choice) {
        case 1:
            ?type? ?variable?
            break;
        case 2:
            ;
            break;
        }
    }

    cout << "Good bye." << endl;

    return 0;
}
  
![Lab1-3 Debugger](https://user-images.githubusercontent.com/79815877/172033831-b612f5cd-4a0f-4b1a-8053-9cc8a7d45dfb.jpg)
  
As you can see, it wants me to figure out what the type and variable will be to execute the code correctly. So my enhancement of the code is to figure out they type and variable, and execute the output.
  
*UPDATE*

After much typing and troubleshooting, I was able to figure out a type and variable that would work. I also ran into an issue with getline(). In order to fix the getline() issue, I had to add #include <string>. See code below:
  
//============================================================================
// Name        : Lab1-3.cpp
// Author      : Alfredo Gomez
// Version     : 1.0
// Copyright   : Copyright © 2017 SNHU COCE
// Description : Lab 1-3 Up to Speed in C++
//============================================================================

#include <algorithm>
#include <iostream>
#include <string>

using namespace std;

//============================================================================
// Global definitions visible to all methods and classes
//============================================================================
double strToDouble(string str, char ch);
// FIXME (1): Define a data structure to hold bid information together as a single unit of storage.
struct Bid {
    string Title;
    string Fund;
    string Vehicle;
    double amount;
};

// FIXME (4): Display the bid values passed in data structure
/**
 * Display the bid information
 *
 * @param ?type? data structure containing the bid info
 */
void displayBid(Bid bid) {
    cout << "Title: " << bid.Title << endl;
    cout << "Fund: " << bid.Fund << endl;
    cout << "Vehicle: " << bid.Vehicle << endl;
    cout << "Bid Amount: " << bid.amount << endl;

    return;
}

// FIXME (3): Store input values in data structure
/**
 * Prompt user for bid information
 *
 * @return data structure containing the bid info
 */
Bid getBid() {
    Bid someBid;

    cin.ignore();
    cout << "Enter title: ";
    getline(cin, someBid.Title);

    cout << "Enter fund: ";
    cin >> someBid.Fund;

    cin.ignore();
    cout << "Enter vehicle: ";
    getline(cin, someBid.Vehicle);

    cin.ignore();
    cout << "Enter amount: ";
    string strAmount;
    getline(cin, strAmount);
    someBid.amount = strToDouble(strAmount, '$');

    return someBid;
}

/**
 * Simple C function to convert a string to a double
 * after stripping out unwanted char
 *
 * credit: http://stackoverflow.com/a/24875936
 *
 * @param ch The character to strip out
 */
double strToDouble(string str, char ch) {
    str.erase(remove(str.begin(), str.end(), ch), str.end());
    return atof(str.c_str());
}


/**
 * The one and only main() method
 */
int main() {

    // FIXME (2): Declare instance of data structure to hold bid information
    Bid theBid;

    // loop to display menu until exit chosen
    int choice = 0;
    while (choice != 9) {
        cout << "Menu:" << endl;
        cout << "  1. Enter Bid" << endl;
        cout << "  2. Display Bid" << endl;
        cout << "  9. Exit" << endl;
        cout << "Enter choice: ";
        cin >> choice;

        // FIXME (5): Complete the method calls then test the program
        switch (choice) {
            case 1:
            	theBid = getBid();
                break;
            case 2:
                displayBid(theBid);
                break;
        }
    }

    cout << "Good bye." << endl;

    return 0;
}
  
![Lab1-3 Code Corrected](https://user-images.githubusercontent.com/79815877/172034167-2aaac81f-2d36-4804-88ad-30e206f0da1e.jpg)


For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/alfredogomez2005/alfredogomez.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
