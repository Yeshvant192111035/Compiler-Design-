%{
#include <stdio.h>
#include <string.h>
%}

%%
"saveetha"   { printf("sse"); }
.|\n        { putchar(yytext[0]); }
%%

int yywrap() {
    return 1;  // Indicate end of input
}

int main(int argc, char *argv[]) {
    if (argc != 2) {
        fprintf(stderr, "Usage: %s input_file\n", argv[0]);
        return 1;
    }

    FILE *input_file = fopen(argv[1], "r");
    if (!input_file) {
        perror("Error opening file");
        return 1;
    }

    yyin = input_file;
    yylex();

    fclose(input_file);
    return 0;
}
