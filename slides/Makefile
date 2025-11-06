# Build lecture slides for time series

# Commands
PANDOC = pandoc -t beamer --template=default.beamer
PANDOC_RAW = pandoc
RM = rm -f

# Files
TGT = ai_economist.pdf

# Rules
default: $(TGT)

lecture: default

all: default

clean:
	$(RM) $(TGT)

template:
	$(PANDOC_RAW) -D beamer

%.pdf : %.md default.beamer
	$(PANDOC) $< -o $@
