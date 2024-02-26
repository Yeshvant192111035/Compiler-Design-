%{
#include <stdio.h>
int line_num = 1;
%}

DIGIT       [0-9]
LETTER      [a-zA-Z]
ID          {LETTER}({LETTER}|{DIGIT})*
NUM         {DIGIT}+
WS          [ \t\n]

%%

"/*"        { while(1) { if(yytext[0]=='\n') line_num++; input(); if(yytext[0]=='*' && input()=='/') break; } }
"//"        { while(1) { if(yytext[0]=='\n') { line_num++; break; } input(); } }
"include"   { printf("INCLUDE: %s\n", yytext); }
"int"       { printf("DATATYPE: %s\n", yytext); }
"void"      { printf("DATATYPE: %s\n", yytext); }
"printf"    { printf("PRINTF: %s\n", yytext); }
"main"      { printf("MAIN: %s\n", yytext); }
"{"         { printf("LEFT_BRACE\n"); }
"}"         { printf("RIGHT_BRACE\n"); }
"="         { printf("ASSIGN\n"); }
","         { printf("COMMA\n"); }
";"         { printf("SEMICOLON\n"); }
\"[^"\n]*\"  { printf("STRING: %s\n", yytext); }
{ID}        { printf("IDENTIFIER: %s\n", yytext); }
{NUM}       { printf("NUMBER: %s\n", yytext); }
{WS}        ;  // Ignore whitespace

.           { printf("UNKNOWN: %s\n", yytext); }

%%

int main() {
    yylex();
    return 0;
}
