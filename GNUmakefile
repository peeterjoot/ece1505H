THISDIR := ece1505-convex-optimization
THISBOOK := ece1505

BIBLIOGRAPHY_PATH := classicthesis_mine
HAVE_OWN_CONTENTS := 1
#HAVE_OWN_TITLEPAGE := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex
BOOKTEMPLATE := ../latex/classicthesis_mine/ClassicThesis2.tex

include make.revision
include ../latex/make.bookvars

# comment this out for online pdf version (uncomment for KDP)
#PRINT_VERSION := 1
#ifdef KINDLE_VERSION
#PARAMS += --kindle
#endif
ifdef PRINT_VERSION
SUBFIGDIR := bw
else
SUBFIGDIR := color
endif
ifndef PRINT_VERSION
PARAMS += --no-print
endif
#PARAMS += -subfig $(SUBFIGDIR)
#DISTEXTRA := $(SUBFIGDIR)
ifdef PRINT_VERSION
#DISTEXTRA := $(DISTEXTRA).kdp
DISTEXTRA := kdp
endif

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
FIGURES := ../figures/$(THISBOOK)
SOURCE_DIRS += $(FIGURES)

#GENERATED_SOURCES += matlab.tex 
#GENERATED_SOURCES += mathematica.tex 
#GENERATED_SOURCES += julia.tex 
GENERATED_SOURCES += backmatter.tex
 
EPS_FILES := $(wildcard $(FIGURES)/*.eps)
PDFS_FROM_EPS := $(subst eps,pdf,$(EPS_FILES))

THISBOOK_DEPS += $(PDFS_FROM_EPS)
#THISBOOK_DEPS += macros_mathematica.sty

#CLEAN_TARGETS += ps5mathematica.tex ps9mathematica.tex

SPELLCHECK := $(patsubst %.tex,%.sp,$(wildcard *.tex))

include ../latex/make.rules

all :: l9
#all :: p2

.PHONY: p2 l9
#p1 : ProblemSet1.pdf
p2 : ProblemSet2.pdf
l9: convexOptimizationLecture9.pdf

ProblemSet1.pdf :: ProblemSet1Problem8.tex
ProblemSet1.pdf :: ProblemSet1Problem7.tex
ProblemSet1.pdf :: ProblemSet1Problem6.tex
ProblemSet1.pdf :: ProblemSet1Problem5.tex
ProblemSet1.pdf :: ProblemSet1Problem4.tex
ProblemSet1.pdf :: ProblemSet1Problem3.tex
ProblemSet1.pdf :: ProblemSet1Problem2.tex
ProblemSet1.pdf :: ProblemSet1Problem1.tex

ProblemSet2.pdf :: ProblemSet2Problem1.tex
ProblemSet2.pdf :: ProblemSet2Problem2.tex
ProblemSet2.pdf :: ProblemSet2Problem3.tex
ProblemSet2.pdf :: ProblemSet2Problem4.tex
ProblemSet2.pdf :: ProblemSet2Problem5.tex
ProblemSet2.pdf :: ProblemSet2Problem6.tex
ProblemSet2.pdf :: ProblemSet2Problem7.tex
ProblemSet2.pdf :: ProblemSet2Problem8.tex
ProblemSet2.pdf :: ProblemSet2Problem9.tex
ProblemSet2.pdf :: ProblemSet2Problem10.tex

.PHONY: spellcheck
spellcheck: $(SPELLCHECK)

%.sp : %.tex
	spellcheck $^
	touch $@

scrpage2.sty : ../latex/scrpage2.sty
	cp $^ $@

#julia.tex : ../julia/METADATA
#mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA

#backmatter.tex: ../latex/classicthesis_mine/backmatter_with_parts.tex
#	rm -f $@
#	ln -s ../latex/classicthesis_mine/backmatter_with_parts.tex backmatter.tex

backmatter.tex: ../latex/classicthesis_mine/backmatter_with_parts.tex
	rm -f $@
	ln -s ../latex/classicthesis_mine/backmatter2.tex backmatter.tex
