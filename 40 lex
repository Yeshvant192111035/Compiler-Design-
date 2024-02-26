%{
#include <stdio.h>
%}

WORD        [a-zA-Z]+
RELOP       "<"|">"|"=="|"!="|"<="|">="

%%

{WORD}      { printf("Word: %s\n", yytext); }
{RELOP}     { printf("Relational Operator: %s\n", yytext); }

.           ;  // Ignore other characters

%%

int main() {
    printf("Enter a statement:\n");
    yylex();
    return 0;
}
