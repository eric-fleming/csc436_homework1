# Homework #1 (by Eric Fleming)

[GitHub Website Link](https://github.com/mrfleming/csc436_homework1) </br>
[Github Clone Reference](https://github.com/mrfleming/csc436_homework1.git) </br>

There were two main goals for this assignment.
1.  Create a function which reverses an array
2.  Clean a string, remove characters you don't want.

## Comments on Implementation
First I looked at the html file to get a sense of the structure of the elements on the website; which was minimal.  The majority of the page is created by adding html elements to the page through JavaScript - adding the reversed array.

#### Some modifications I made to the original code
1.  I added methods to the run() method
2.  I refactored clearDocument() out of the documentInit() and placed it as the first call in the run method
3.  I added numerous helper functions to simplify getting and processing data
4.  I reduced the size of some commments by using the // notation inplace of /**/ at some locations
5.  I created a HEAD-tag and moved the style tag inside; I moved the script tags inside the html element (I think the browser just auto-corrected these errors upon compilation but I figured I would save it the effort.)

#### Reversing the array
I made an empty array to be filled later.  I then iterated through the original startup array which was a global variable from the scripts reference frame and loaded it in reverse order.  Returning the new reversed copy.

#### Cleaning a string
I assumed that numbers were not special characters.  I wrote a helper function **alphaNumeric** which essentially is a predicate to determine if a character is special or not.  If alphaNumeric returns true, you should use that character to build a new string, but if it is flase you should skip it.  I also assumed space characters were "allowable".  This means that if a space was found at the end or the beginning of a string, it would remain in the new string.  I also wrote a second helper function **doubleTrim** to apply both trimming operations for me.  One case I did not clean is what if someone put too many spaces in the middle of two words in a string.  For example, "this       has many spaces...".  If I wanted to get rid of that I would have to look up string pattern matching to see if a string contained an index for multi-space substrings, then return a new string where I slice it out and concatenate it the former and later pieces.  The browser already contained some logic for not displaying these situations so I left it as is.  
In the element attribute list there is a subtle difference between innerHTML and innerText.  If the innerText has too many spaces, they will not show up in the innerHTML, but the length of the string will be reported as longer than it appears.