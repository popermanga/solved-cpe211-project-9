Download Link: https://assignmentchef.com/product/solved-cpe211-project-9
<br>
<strong></strong>&lt;Project 9 Description&gt;




Project 9 introduces the student to the use of structures in programming.  This assignment will tie in several of the key areas previously used in the lab assignments.  In particular, input from a file, output to a file, functions (value returning and void), if statements, while loops (or some other form of looping) and others.  <strong><em>You are not allowed to use arrays in this program!!!</em></strong>




Problem description: You are writing the subscription renewal system for a magazine.  Information for each subscriber is kept in a file.  The information for one subscriber is called a record, and the input file may contain several records or no records.  After reading each record, a test is made to determine if the subscribers’ subscription has expired.  If a subscribers’ subscription is still active (number of months left on subscription is greater than 0), no action is necessary and the next record is obtained.  If a subscribers’ subscription has expired (number of months left on subscription is 0), information about the subscription is written into an output file before the next record is obtained.

You may run the sample solution <strong>Project_09_solution</strong> by typing the following at a command prompt in a terminal window<strong>:  </strong>

<strong> </strong>

<h1>/home/work/cpe211/Executables/Project_09/Project_09_solution</h1>

<em><u>(Input files are contained in P9_in.zip)</u> </em>




The comparison script can be run by using the following command

<h1>/home/work/cpe211data/Project_09/CompareSolution.bash Project_09.cpp</h1>







<h2>&lt;Project 9 Directions&gt;</h2>




<strong><em>On Project 9, you may only use concepts presented in Chapters 1 – 10 of your textbook!! </em></strong>

The following specific concepts are not allowed at all: Global Variables, Arrays and Recursive Function Calls.  All function calls are made from main only.

<strong>The input file can be opened one time only</strong>




<strong><em>Use of global variables, arrays, or recursive calls will result in zero credit (0).</em></strong>




<strong><em>In addition to the function</em></strong> <strong>main()</strong>, <strong><em>your solution must include <u>at least the four functions</u> mentioned on item #2 on page 3 of this description to receive full credit.  For each of these functions, only one of the parameters may be a structure variable and this structure variable must be a top level structure (see structure information on page 2) variable.</em></strong>




Using your favorite text editor, type your solution and save it as a file named <strong>Project_09.cpp</strong> within your <strong>CPE211_FALL18/Project_09 </strong>directory.  If there are syntax errors, correct them and compile again.  Once your program successfully compiles, run it and verify that the output for your modified program matches the output from the solution executable – <strong>Project_09_solution</strong>.

<h2>&lt;Project 9 Structure Details and Other Hints&gt;</h2>

<strong> </strong>

<strong>Read the entire project handout before writing any code, think about it, read it again, plan out your solution (write a functional decomposition or draw your own flow chart to organize your solution), and then write and test your code. </strong>

<strong> </strong>

<ol>

 <li><strong><em>There are 5 structure DataTypes that must be declared</em></strong>. These must be <strong><em>global</em></strong> struct declarations (place these declarations after the <strong>using namespace std;</strong> statement and before your function prototypes). NOTE: VARIABLES DECLARED AS THE DATA TYPE OF THE STRUCTURE ARE NOT TO BE DECLARED AS GLOBAL VARIABLES.  The structures will be written in a hierarchical fashion.  One will be the top-level structure and the other four will be sub structures (see pages 486-488 of the text).</li>

</ol>




<strong>The top-level structure has the following 3 members: </strong>

subscriberName                   (declared as a <strong>Subscriber Name structure</strong>) address                                     (declared as an <strong>Address structure</strong>)

renewal_information            (declared as a <strong>Renewal Information structure</strong>)




Each field of the top-level structure is also a structure, creating a hierarchical structure.  The details of each nested structure are summarized below – be sure to pay attention to the data types of each structure member!!




<strong>The sub structures (nested structures) have the following members: </strong>




<strong>Subscriber Name Structure:</strong>

first name                              (a string)                                 last name                             (a string)

customer id                           (an integer)




<strong>Address Structure</strong><strong>: </strong>

street number and name  (a string) city                                      (a string) state                                       (a string)

zip_code                                (an integer)




<strong>Date Structure</strong><strong>:</strong>

month    (a string) day     (an integer) year     (an integer)




<strong>Renewal Information Structure</strong><strong>:</strong>

number of months left         (an integer) last renewal notice sent        (a <strong>Date</strong> structure)




NOTE: The order in which you declare your structures is important.  The sub structures must be declared <strong><em>before</em></strong> the top-level structure.  Furthermore, the <strong>Date Structure</strong> must be declared before the <strong>Renewal Information Structure</strong>.




<ol start="2">

 <li>This program must include the following 4 functions:

  <ol>

   <li>A function that opens the input file and includes all error-handling logic. If the user-specified file does not open, this function should use a <strong>LOOP</strong> that will repeatedly

    <ul>

     <li>output an error message</li>

     <li>clear (reset) the file stream</li>

    </ul></li>

  </ol></li>

</ol>

<strong>inputStreamVariable.clear();</strong>

<ul>

 <li>reprompt the user and input their next file selection</li>

 <li>attempt to open the next selection until the user-specified file opens successfully or until the user types Control-C to exit the program. <strong><em>Remember – Recursion is not allowed!!</em></strong></li>

</ul>

<ol>

 <li>A function that opens the output file and includes error-handling logic similar to that describe above in <strong>Part a</strong> for opening of the input file. The program is to correctly handle an output file that does not open successfully (see the last page of this document).</li>

 <li>A function that inputs one complete record at a time from the input file and stores the information in the appropriate structure variable fields (member names). You may assume that all fields are present for each record and that the information in those fields is of the appropriate data type. This function could be a Boolean value returning function.  <strong>This function <u>cannot </u>have an ofstream parameter</strong></li>

 <li>A function that writes a subscriber record to the output file if and only if that subscribers’ subscription has expired (number of months left is 0). Run the provided sample solution to obtain a sample of what is to be written to the output file.  <strong>This function <u>cannot</u> have an ifstream parameter</strong></li>

</ol>




<ol start="3">

 <li>For the functions above only one of the parameters can be a structure variable, and this structure variable must be a top level structure variable. <strong>Furthermore, there can be at most 3 parameters for any function </strong>ç</li>

</ol>




<ol start="4">

 <li>The function main() should contain the loop that controls the reading of the records. In main(), two counters are used to keep track of (1) the number of subscribers present in the file and (2) the number of subscribers that have expired subscriptions. <strong>After the last subscriber record has been processed, a message is written to the <u>terminal</u> indicating how many subscribers were in the file and how many subscribers have expired subscriptions</strong>.</li>

</ol>




<ol start="5">

 <li><strong><em>Since there are multiple records possible in an input file and you cannot use arrays – even if you know how, each record is read from the input file, processed, and written to the output file (if necessary) before the next record is read.</em></strong></li>

</ol>




<ol start="6">

 <li><strong><em>Your program will not know in advance the number of records that exist within a file. </em></strong>  An example record of the information in the input file is arranged as follows (NOTE: the information shown as a comment is not present in the input file):</li>

</ol>




<strong>Joe               // First name  </strong>

<strong>Smith             // Last Name </strong>

<strong>14235             // Customer id  </strong>

<strong>123 Abbey Way     // Street Number and Name (must be read with </strong><strong>getline</strong><strong>) </strong>

<strong>Huntsville        // City (must be read with </strong><strong>getline</strong><strong>) </strong>

<strong>Alabama           // State (must be read with </strong><strong>getline</strong><strong>) </strong>

<strong>35789             // Zipcode </strong>

<strong><u>0                 // # of months remaining on subscription</u></strong>

<strong>March             // Last renewal notice month </strong>

<strong>10                // Last renewal notice day </strong>

<strong>2002              // Last renewal notice year </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<ol start="7">

 <li>Sample input files have been provided to the student for testing of the program. The program will be tested with different input files (not available to the students).  The format of the input file used for testing is identical to the format of the sample input files.</li>

</ol>




Reading information from the input file will require statements like the following:




<strong>inputStreamVariable &gt;&gt; structVar.name.first; </strong>

<strong>getline (inputStreamVariable, structVar.address.city,’
’); inputStreamVariable.ignore(INT_MAX,’
’);</strong>




It is up to the student to determine where, when, and how to use these statements.  Note: The above input statements illustrate how information can be read directly into the member of a structure.




<ol start="8">

 <li>If an input file does not contain any records, it will be empty. <strong>For this input file, a message is written to the </strong><strong>output file and to the terminal</strong>.  Run the provided sample solution with the file P9_in4.txt to see the required messages and program operation.</li>

</ol>




<ol start="9">

 <li>When reading in the information for a subscriber, read the first name and then test the input stream to see if it is in the fail state. If it is, do not read any more information from the input file, and then perform any necessary actions based on reaching the end of the file.</li>

</ol>




<ol start="10">

 <li>It is easiest to handle a “empty” input file by using a priming read action before entering a while loop. The priming read in this case will be a read of an entire subscriber record. The file stream can be tested after the priming read (and before the while loop) to see if the eof status bit is true è empty file</li>

</ol>




<ol start="11">

 <li>Remember that input and output streams used as parameters in a function must be reference parameters.</li>

</ol>




<ol start="12">

 <li>When processing a record for a subscriber, print out the phrase “Processing Customer Id: ####” right after the customer id has been read.</li>

</ol>




<ol start="13">

 <li>To test a bad output file, use a file name of Bad/Input/File.txt or any name you want as long as it has a / somewhere in it.</li>

</ol>




<ol start="14">

 <li>To determine the input order and the expected output, run the sample solution <strong>/home/work/cpe211/Executables/Project_09/Project_09_solution</strong></li>

</ol>




<ol start="15">

 <li>Match your output as closely as possible to the output of the sample solution.</li>

</ol>




<ol start="16">

 <li>Don’t forget to run the comparison script to see how your solution compares to the sample solution. <strong>/home/work/cpe211data/Project_09/CompareSolution.bash cpp</strong></li>

</ol>


