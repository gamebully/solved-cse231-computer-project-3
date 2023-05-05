Download Link: https://assignmentchef.com/product/solved-cse231-computer-project-3
<br>
Assignment Overview

This assignment focuses on the design, implementation and testing of a Python program to compute tuition charges at MSU (see below).

Assignment Deliverable

The deliverable for this assignment is the following file:

proj03.py – the source code for your Python program

Be sure to use the specified file name and to submit it for grading via the Mimir system before the project deadline.

Assignment Background

MSU has an on-line tuition calculator:

http://ctlr.msu.edu/COStudentAccounts/TuitionCalculatorFall.aspx

That calculator is based on information such as that posted at:

http://ctlr.msu.edu/COStudentAccounts/Tuition_FeesResident_Undergrad_2019-20.aspx

Assignment Specifications

1. You will develop a Python program which calculates the tuition for an undergraduate MSU student during Fall Semester 2019, based on parameters supplied by the user (such as the student’s residency status and class level).

2. Your program will permit mixed-case input strings. For example, the strings “yes”, “Yes”, “YES” and “yES” will all be processed by your program as equivalent user inputs.

3. The calculated tuition will be displayed with a dollar sign ($) and commas for the thousands. That is, a value of 12345.67 will be displayed as $12,345.67 by your program. Also, even dollar amounts will have zeros for cents (for example, a value of 12 will be displayed as $12.00).

4. The following tables give the necessary values.

College and year Resident Non-Resident &amp; InternationalPer Credit (111) Flat Rate (1218) Flat + Credit (&gt;18) Per Credit (1-11) Flat Rate (1218) Flat + Credit (&gt;18)Core UnitsFreshman $482 $7,230 Flat + credit $1,325.50 $19,883 Flat + creditSophomore $494 $7,410 Flat + credit $1,325.50 $19,883 Flat + creditJunior $555 $8,325 Flat + credit $1,366.75 $20,501 Flat + creditSenior $555 $8,325 Flat + credit $1,366.75 $20,501 Flat + creditEli Broad College of Business &amp; College of EngineeringFreshman $482 $7,230 Flat + credit $1,325.50 $19,883 Flat + creditSophomore $494 $7,410 Flat + credit $1,325.50 $19,883 Flat + creditJunior $573 $8,595 Flat + credit $1,385.75 $20,786 Flat + creditSenior $573 $8,595 Flat + credit $1,385.75 $20,786 Flat + credit

Special Fees (per semester)Part-Time (4 credits or fewer) Full-TimeBusiness – juniors and seniors $113 $226Engineering – admitted $402 $670Health – juniors and seniors $50 $100Sciences – juniors and seniors $50 $100CMSE – juniors and seniors $402 $670International $375 $750

Student-Voted Taxes (per semester)ASMSU Tax – all undergraduate students $21FM Radio Tax – all students $3State News Tax – all students with 6 or more credits $5James Madison College Student Senate Tax – all students in James Madison College $7.50

5. “flat + credit”: Students taking more than 18 credits calculate their tuition by starting with the flat fee and adding on the specified per-credit for each credit greater than 18. For example, a student taking 20 credits pays the flat rate plus 2*(per-credit). The “per-credit” value is the value in the “per-credit (1-11) column.

6. Input Specification and Ordering: To facilitate grading the input must be in the following order:a) Resident (yes/no):b) If not resident, International (yes/no):c) Level—freshman, sophomore, junior, senior:d) If level is junior or senior, ask for College.College—business, engineering, health, sciences, none:e) If level is junior or senior ask if major is CMSE (“Computational Mathematics and Engineering”) (yes/no)f) If level is freshman or sophomore, ask if admitted to College of Engineering (yes/no):g) If college not business, engineering, health or sciences, ask if James MadisonCollege (yes/no)h) Creditsi) Ask if the user wants to do another calculation.

Assignment Notes

1. To clarify the project specifications, sample output is provided at the end of this document.

2. Your program must accept user inputs in the order specified.

3. Python 3 provides formatting for the dollar output. A comma (,) causes commas to be properly placed in numbers. Note that the ordering matters so that comma is placed immediately after the colon and before other formatting marks, e.g. {:,.2f} Experiment in the shell.

4. The string method lower() can be used to convert all letters in a string to lower case. This is particularly useful for input, that is you can handle “yEs”, “yeS”, “YEs”, etc by converting the input to lower case and checking against “yes”.

5. The Python None is a useful default initialization for variables that may not be assigned a value. For example, not everyone is asked for their college so initializing college to None can be handy because None evaluates as False in a Boolean expression.college = None if college:print(“this will not print if college has the value None”)

6. Notes on handling input errors:• For “yes/no” questions, assign all answers that are not “yes” to be “no” .• For the question about college that has an option of “none”, assign any answer to be “none” (or None, if you wish) for any response that is not one of the specified colleges.• For level, if the answer is not one of the specified responses (“freshman”, etc.), you must print an error message “Invalid input. Try again.” and re-prompt until you get a specified response.• For credits, input must be an integer greater than zero. Print an error message “Invalid input. Try again.” and re-prompt until you get an integer greater than zero. Hint: the string isdigit() method useful here.

7. Common error to avoid. You might like to use a Boolean expression such as this:level == ‘freshman’ or ‘sophomore’ or ‘junior’ or ‘senior’Unfortunately, that expression always evaluates to True because any non-empty string isTrue so it is effectively: level == ‘freshman’ or True or True or TrueInstead use the following(level == ‘freshman’) or (level == ‘sophomore’) \ or (level == ‘junior’) or (level == ‘senior’)

8. You are responsible for following the coding standard items 1-6

9. You are not allowed to use advanced data structures such as list, dictionaries, classes, etc. However, you are allowed to read ahead and use try-except and functions.

10. “Hard-coded answers” will receive a zero score for the project. That is, if you design your code to handle the specific test cases rather than the general problem, you will not get credit.

Sample Output

TEST 1

2019 MSU Undergraduate Tuition Calculator.

Resident (yes/no): yesLevel—freshman, sophomore, junior, senior: freshmanAre you admitted to the College of Engineering (yes/no): noAre you in the James Madison College (yes/no): noCredits: 12Tuition is $7,259.00.Do you want to do another calculation (yes/no): no

TEST 2

2019 MSU Undergraduate Tuition Calculator.

Resident (yes/no): yesLevel—freshman, sophomore, junior, senior: JuniorEnter college as business, engineering, health, sciences, or none: businessIs your major CMSE (“Computational Mathematics and Engineering”)(yes/no): NoCredits: 17Tuition is $8,850.00.Do you want to do another calculation (yes/no): no

TEST 3

2019 MSU Undergraduate Tuition Calculator.

Resident (yes/no): yEsLevel—freshman, sophomore, junior, senior: SeniorEnter college as business, engineering, health, sciences, or none: engineeringIs your major CMSE (“Computational Mathematics and Engineering”)(yes/no): noCredits: 5Tuition is $3,559.00.Do you want to do another calculation (yes/no): YesResident (yes/no): nOInternational (yes/no): yesLevel—freshman, sophomore, junior, senior: sophomoreAre you admitted to the College of Engineering (yes/no): yesCredits: 20Tuition is $23,983.00.Do you want to do another calculation (yes/no): no

TEST 4

2019 MSU Undergraduate Tuition Calculator.

Resident (yes/no): yesLevel—freshman, sophomore, junior, senior: xxxInvalid input. Try again.Level—freshman, sophomore, junior, senior: yyyInvalid input. Try again.Level—freshman, sophomore, junior, senior: juniorEnter college as business, engineering, health, sciences, or none: abcdIs your major CMSE (“Computational Mathematics and Engineering”)(yes/no): yesAre you in the James Madison College (yes/no): noCredits: 0Invalid input. Try again.Credits: abInvalid input. Try again.Credits: 3.5Invalid input. Try again.Credits: 11Tuition is $6,804.00.Do you want to do another calculation (yes/no): no

Grading Rubric

Computer Project #3Scoring Summary

General Requirements:(4 pts) Coding Standard 1-6(descriptive comments, mnemonic identifiers, format, etc…)

Implementations:

(4 pts) Test 1(4 pts) Test 2(4 pts) Test 3(4 pts) Test 4