TARGET = usermanual_jp
SOURCE = $(TARGET).tex compile.tex configuration.tex \
    editdoc.tex others.tex preface.tex whatsnew.tex
OTHER_TEX = cursorobjtab.tex editobjtab.tex

TEX = uplatex
DVIPDF = dvipdfmx

all: pdf

.PHONY: pdf
pdf: $(TARGET).pdf
$(TARGET).pdf: $(TARGET).dvi
	$(DVIPDF) $(TARGET)

.PHONY: dvi
dvi: $(TARGET).dvi
$(TARGET).dvi: $(TARGET).aux
	$(TEX) -halt-on-error $(TARGET)

$(TARGET).aux: $(SOURCE)
	$(TEX) -halt-on-error $(TARGET)

.PHONY: clean
clean:
	rm -f $(TARGET).dvi $(TARGET).pdf $(SOURCE:%.tex=%.aux) $(TARGET).log $(TARGET).toc $(TARGET).lof $(TARGET).lot $(TARGET).out $(SOURCE:%.tex=%.tex~)
