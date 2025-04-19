# caesar_cipher
In this project I will write a caesar cipher which will take in a string and
a number for the offset, shift the letters with a right shift, and return
the modified string.

Reflections:
A few bugs popped up as I was writing this.  By using the stack trace, I was able to track down where the bugs were originating and then by using pry-byebug I was able to check my variables during runtime.

The first error was in the string index assignment.  Checking character against it's upcase didn't work for punctuation and allowed the program into the assignment as nil values instead of kicking it to the else statement, causing an error.

After fixing the first bug another bug popped up, this time
I was erroneously checking index.class against numeric instead of Interger, which caused the array of indexes to be nothing but nil values, causing an error when the program got to the shifted string characters index comparison.  Checking the ruby documentation revealed my error and changing the class check to Integer solved the issue.

Once the program was running without errors the output was a long line of numbers.  I had a hunch it was in the shifted string characters assignment.  Using pry-byebug and checking variables I was able to fix the assignment and the program returned the appropriate letters.

The final bug was the program removing all spaces and punctuation.  The fix for this was to modify the shifted string index assignment into a do..end block and add an else statement to pass the current value.  This prevented stripping spaces and punctuation.

I am grateful for the chance to do this project as it gave me the opportunity to really practice using map to transform values back and forth, using modulus to ensure the program would wrap values to the start of the array when shifting letters at the end of the alphabet, using logic statements and operators, and using the debugger and stack trace to track down errors and unintended bugs.
