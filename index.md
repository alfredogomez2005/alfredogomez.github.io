## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/alfredogomez2005/alfredogomez.github.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

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



**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/alfredogomez2005/alfredogomez.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
