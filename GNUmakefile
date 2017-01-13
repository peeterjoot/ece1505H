THISDIR := ece1505-convex-optimization
THISBOOK := ece1505

include ../latex/make.bookvars

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
FIGURES := ../figures/$(THISBOOK)
SOURCE_DIRS += $(FIGURES)

# also toggle redacted classicthesis-config.tex
# FIXME: changing this flag should be a dependency of matlab.tex 
#REDACTED := -redacted

#GENERATED_SOURCES += matlab.tex 
#GENERATED_SOURCES += mathematica.tex 
#GENERATED_SOURCES += julia.tex 

EPS_FILES := $(wildcard $(FIGURES)/*.eps)
PDFS_FROM_EPS := $(subst eps,pdf,$(EPS_FILES))

THISBOOK_DEPS += $(PDFS_FROM_EPS)
#THISBOOK_DEPS += macros_mathematica.sty

#CLEAN_TARGETS += ps5mathematica.tex ps9mathematica.tex

include ../latex/make.rules

p1 : convex-optimizationProblemSet1.pdf

l2: convex-optimizationLecture2.pdf

convex-optimizationProblemSet1.pdf :: convex-optimizationproblemSet1Problem8.tex convex-optimizationproblemSet1Problem7.tex convex-optimizationproblemSet1Problem6.tex convex-optimizationproblemSet1Problem5.tex convex-optimizationproblemSet1Problem4.tex convex-optimizationproblemSet1Problem3.tex convex-optimizationproblemSet1Problem2.tex convex-optimizationproblemSet1Problem1.tex

all :: p1
#all :: convexL1.pdf

#julia.tex : ../julia/METADATA
#mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA
