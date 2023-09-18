regex101
a     -Match a letter
.      -match anything
^a  -Start with letter
b$  -end with letter
k*  -any number of this letter
\[a-z\]    -start with any of the letters
\[^a-z\]   -anything but the letters between, you have to specify capitals
\. \\\[  \\\*      -match the special characters
(a.b) \\1   -has to have letters repeating
a|b         -or
c+          -1 and more
d?          - 0 and 1 time
{9}         -match the pattern 9 times
{,9}        -match 9 or less occurrences