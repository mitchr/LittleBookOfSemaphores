VIEWER = atril

PDFFLAGS = -dCompatibilityLevel=1.4 \
           -dCompressPages=true -dUseFlateCompression=true  \
           -dEmbedAllFonts=true -dSubsetFonts=true -dMaxSubsetPct=100

NAME = LittleBookOfSemaphores

$(NAME).ps: book.tex
	latex book
	bibtex book
	makeindex book
	latex book
	latex book
	dvips -Ppdf -o $(NAME).ps book

distrib: $(NAME).ps
	ps2pdf $(PDFFLAGS) $(NAME).ps $(NAME).pdf

view: $(NAME).ps
	$(VIEWER) $(NAME).ps

clean:
	rm -f book.aux book.bbl book.blg book.dvi book.idx book.ilg book.ind book.log book.out book.toc $(NAME).pdf $(NAME).ps out
