BASENAME = template
PDF = $(addsuffix .pdf, $(BASENAME))
TEX = $(addsuffix .tex, $(BASENAME))
PDFLATEX = pdflatex
OUT_DIR = texfiles

# Change it to point to the template, use something like `../../../template/`
STY_DIR = .

.PHONY: clean all

all: $(PDF)

$(PDF): $(TEX)
	test -d $(OUT_DIR) || mkdir $(OUT_DIR)
	# Twice, so TOC is also updated
	TEXINPUTS=$(STY_DIR)//: $(PDFLATEX) -output-directory $(OUT_DIR) $<
	TEXINPUTS=$(STY_DIR)//: $(PDFLATEX) -output-directory $(OUT_DIR) $<
	mv $(OUT_DIR)/$(PDF) .

clean:
	rm -rf $(OUT_DIR)
	rm -f $(PDF)
