# globing
Function in C largely inspired by glob (3).

int     match(char *tested, char *word);

Returns 1 if *tested matches with word in terms of reg exp ('*', '?', '[', ']').
Returns 0 if no match is found.

The only exception with regular expressions is the fact that "[a-f]" will not try to match any character between a and f,
but 'a', '-' or 'f'.

The function is case sensitive.

For instance: 
if word is "*", it will match whatever word passed in tested.
if word is "*[coh], it will match whatever word that ends with 'c' OR 'o' OR 'h'.
if word is "???*hello*", it will match whatever word that starts with 3 letters and then contains hello. 
"???*hello*" matches with "FooBarhello", "With helloawd", but not with "hello" or "ashello".
