CC = cc
LEXER = flex
PARSER = bison -t

all : psh_parser

psh.tab.c psh.tab.h : psh.y
	$(PARSER) -d $<

lex.yy.c : psh.l psh.tab.h
	$(LEXER) $<


psh_parser : lex.yy.c psh.tab.c psh.tab.h
	$(CC) -o $@ psh.tab.c lex.yy.c -lm
