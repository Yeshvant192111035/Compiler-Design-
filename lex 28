%{
#include <stdio.h>

int vowel_count = 0;
int consonant_count = 0;
%}

VOWEL       [aeiouAEIOU]
CONSONANT   [bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ]
SPACE       [ \t\n]

%%

{VOWEL}     { vowel_count++; }
{CONSONANT} { consonant_count++; }
{SPACE}     ;  // Ignore spaces, tabs, and newlines

.           ;

%%

int main() {
    printf("Enter a sentence: ");
    yylex();
    printf("Number of vowels: %d\n", vowel_count);
    printf("Number of consonants: %d\n", consonant_count);

    return 0;
}
