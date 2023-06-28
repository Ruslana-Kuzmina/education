# Requirements

## 1. Description 

The given system is designed for choosing and ordering lunch at the cafeteria in
advance by company employees. It allows reducing time spent on dishes selection
on-site and preventing from over-consumption of food supplies. On top, it allows
paying for orders by deducting the order amount from salary. 

## 2. Generic System view

Any user originally lands on the authorization page. After providing the credentials
(login and password), the user gets directed to the corresponding application interface
page, depending on his/her rights. The system comprises of two application parts:
the users’ one (for users without privileges) which allows placing an order only;
and the administrative one (for users with administrative rights) which allows
creating the menu and viewing the orders.

- Section A (Registration by using a corporate account)
    - Question A1: What the authentication fields are displayed on the main page:
                   login, password or another?
    - Question A2: Is there a field where you can enter your corporate email?
    - Question A3: How is the validation of email going on?
    - Question A4: Does the button use for submitting the entered data or the user
                   should use the button "Emter" on a keyboard?
    - Question A5: Does a notification pop up if an incorrect email is entered?
    - Question A6: Does a redirection to the company's website exist for authentication?
    - Question A7: Will the authentication only be going on the company's website?
    - Question A8: Will both authentication and authorization be going on the
                   company's website?
    - Question A9: After a successful authentication on the company site will the
                   notification appear?
    - Question A10: If the authorization belong to the application, how long should
                    it compare the employee's email and his rights?

- Section B (Registration when the credentials are sended to email)
    - Question B1: When does the registration pass on the website after receiving
                   the credentials to the email?
    - Question B2: After passing the registration, is it necessary to change the
                   password to a new one?
    - Question B3: Does an opportunity exist on the site to recover the password
                   if the user forgot it?
    - Question B4: Who has to send the credentials to the user?
    - Question B5: Does the notification "The Remember my credentials on this computer"
                   pop up after a successful registration?

- Section C (Registration himself)
    - Question C1: Does the site have a registration page?
    - Question C2: Does the site have a field "Login"?
    - Question C3: Is it possible to specify an email from the user as a Login?
    - Question C4: Is it possible to specify a mobile phone number as a Login?
    - Question C5: Is it possible to specify a unique name as a Login?
    - Question C6: How many characters does the Login field contain?
    - Question C7: Could the Login field contain the digits?
    - Question C8: Could the Login field include the special characters (( ) , . / : ; ! ?)?
    - Question C9: Could the Login and password be the same word?
    - Question C10: How many characters does the Password field contain?
    - Question C11: Could the Password field consist of only digits?
    - Question C12: Is it possible to use the space character in the Login field?
    - Question C13: Is it possible to use only ASCII characters in the Login and
                    Password fields?
    - Question C14: Is it possible to use Unicode characters in the Login and
                    Password fields?
    - Question C15: If an email is used as a Login, will a confirmation email be
                    received after a successful registration?
    - Question C16: If a mobile phone number is used as a Login, will SMS be received
                    after a successful registration?
    - Question C17: Will the right be to only order food for new users by default?

## 3. Functional requirements 

### 3.1. Types of Users

There are two types of users in the system: employees who place orders, and administrators
who create the menu and view the orders. The users are created and stored in the
database (see 4.1).

3.2 User Application

3.2.1 Main Screen

Upon authorization, a regular user gets directed to the user application interface.
Immediately, the system checks whether the current time is within the timeslot allowed
for placing an order (see 3.2.3) and whether the user already placed any order. If
an order has already been made, the user gets directed to the order screen (see 3.2.2).
If the current time does not meet the allowed slot, a notification appears “Sorry,
unfortunately we do not accept any more orders for today”. If the time is acceptable
and yet no orders are made, then the screen displays the list of dishes (the menu)
available for today; the multiline field with selected dishes (empty by default);
two arrows: the right one – which moves a selected dish from the menu list into the
order field, and the left one – which returns the selected dish from the order area
back into the menu; and the buttons “Order” and “Log off”. 
The menu represents the list of dishes split into the categories: soup, meat, side
dish, and dessert. Each dish has its price marked in its line. The price might consist
of 5 digits. To move the selected dish from the menu into the order area, the user
needs to highlight the dish and click the right arrow. To remove any dish from the
order area, the user needs to highlight it and click the left arrow. To confirm
the order, the user needs to click the button “Order”. The payment for the order
is done in accordance with section 3.4 rules. The user gets directed to the order
screen (see 3.2.2). To exit the system, the user needs to click the button “Log off”.

- Section D (The price):
    - Question D1: The contradiction in the requirements: in the requirement 3.2.1
                   is written that the price must consist of 5 symbols. And in the
                   requirement 3.3.1 is written that the price should be from 2 to
                   6 characters. I would like to clarify how many characters should
                   price field contain?
    - Question D2: I would like to clarify if only integer values are allowed or
                   non-integer values also to the price?
    - Question D3: Will the separator be considered as a single character in a price?
    - Question D4: What kind of separator will it have: dot or comma?
    - Question D5: Will the field Currency exist in the menu?

- Section E (The order):
    - Question E1: Can a user book two identical dishes in one order?
    - Question E2: How many levels of nesting is possible for each category?
    - Question E3: If the user order the dish from one of the categories is it
                   possible to move to another category?
    - Question E4: What is the limit of the number of dishes in one order?
    - Question E5: Is it possible to find out if there is a maximum sum per one order?
    - Question E6: What is the maximum number of each dish that can be cooked in the kitchen?
    - Question E7: Are all the dishes indicate on the site available to order?
    - Question E8: If a user ordered a dish that is unavailable for order, will a
                   notification pop up "Dear user, this dish is unavailable for order. We apologize."?
    - Question E9: If the kitchen doesn't take ane orders to the dishes, will it
                   be removed from the current menu?
    - Question E10: Who will remove the dishes that aren't available for order?
    - Question E11: How often will the information be updated about the dishes that
                    can't be ordered, but they are on the menu?
    
- Section F (Button Log off)
    - Question F1: For a better understanding for the user of the button's function Log off, can we rename the button Exit,
    - Question F2: Can we create a button Lop out to redirect the userto the registration page, where he entered the login and password?
    

3.2.2 Order screen

The given screen displays the information on the ordered dishes, the total order sum and locates the buttons “Edit”, “Cancel” and “Log off”. The button “Edit” serves to edit the existing order; once the user clicks the button, he/she is redirected to the Main screen of the user application. The button “Cancel” will cancel the placed order. The action is available up till 12:00:00 pm. If the current time is past 12:00 pm, the button “Cancel” gets disabled. The button “Log off” will log off the user from the application.

3.2.3 Defined Timeslot for placing orders

An order can be placed every working day from 7:00 am till 12:00 pm in the morning. If a user started placing an order before 11:59:59 am and finished at 12:00:00 pm and later, such an order is not accepted. 

3.3 Administrator application interface

Upon authorization, a user with administrative rights gets directed to the Administrator application interface, which consists of two tabs: “Menu creation” and “Today’s Orders”. By default, the user gets to the menu creation tab.

3.3.1 “Menu creation” tab

The given tab consists of: the dropdown list with the menu categories, the dish name, the price, the multiline menu field, the buttons “Add to menu”, “Remove from menu”, “Publish” and “Log off”.
The menu categories list the following: soup, meat, side dish, dessert. By default, the first value is selected – soup. The dish name’s field can be of 120 characters length, including all the Cyrillic and Latin letters, numbers and the following special symbols: ( ) , . / : ; ! ?. The price field can contain from 2 to 6 characters, and supports only digits.
The button “Add to menu” checks for the dish name and price values to be filled in within the current field; and if the latter ones are present, adds the given dish into the corresponding menu category and displays it in the multiline menu field. If the dish name field and / or price is empty, the error message dialog pops up “Please check, you might have forgotten to fill in the dish name field and / or price field” with OK button.
The multiline menu field appears as the following tree-like hierarchy: a category is displayed first, then all its belonging dishes, then next category comes with all of its dishes displayed, etc.
If any of the dishes has to be removed from the menu, the user needs to highlight it and click the button “Remove from menu”. If no entries in the menu are highlighted, the button “Remove from menu” is disabled.   
The button “Publish” allows making the current menu visible in the user application interface. The menu has to be published starting from 12:00:00 pm of a current day when placing an order gets already unavailable for users, till 6:59:59 am next day. Friday – is an exception, when the menu can be published from 12:00:00 pm on Friday till 6:59:59 am on Monday. In this case at 7:00:00 am the menu becomes visible and available in the user application interface. If by this time the menu is not published, an empty menu list is displayed in the user application interface.
The button “Log off” allows exiting the application.

3.3.2 Tab “Today’s Orders” 

The current page displays all the information about the orders placed for today. It gets updated every working day at 12:00:00 pm when users can no longer make an order.
The page consists of: the table with the orders, the inactive field “Total orders sum” and the button “Log off”. 
The table with the orders represents a regular menu view (the same as in the user application interface), but each dish now has the number of ordered portions to the right. 
The inactive field “Total orders sum” displays the total sum for all the orders placed for today. 

The button “Log off” allows exiting the application. 

3.4 Order Payment

Upon clicking the button “Order”, the system records the user’s order information into the database. If the user edits his/her order by 12:00:00 pm, the database entries are also modified. At 12:00:00 pm, all data on the orders is sent via e-mail to the accounting department, where the order sum is deducted from the employee’s salary. 

- Section G (Payment):
    - Question G1: What kind of form does the order data send to the accounting department?
    - Question G2: How often does the order information send to the accounting department
    - Question G3: Will the user receive the information about the order to the e-mail?
    - Question G4: What kind of system will it be used to send the order to the accounting department?

4 Non-Functional Requirements

4.1 Platform

The system should be developed for MS SQL 2016, IIS 7.0 and ASP.NET Core 1.0.

4.2 Computer / Hardware Requirement

The application is designed to work with the screen resolution of 1024 x 768, though it can also support a higher resolution. It requires 150 MB of space on the hard drive, and the processor with the frequency of at least 800 MHz.

- Section H (Computer):
    - Question H1: What type of this application is it: a mobile application or a web application?
    - Question H2: What OS versions will the site support?
    - Question H3: What type of the browser will the site support?
    - Question H4: What devices will the application run on: mobile phone or laptop?
    - Question H5: What screen orientation does the application support: the portrait and/or
                landscape?
    - Question H6: If an error is happend on the server, will a notification display to the users about this error?
    - Question H7: What language will the application support?
    - Question H8: Will the user have a possibility to add a new language to the application?
    - Question H9: What language will it install on the application by default?



