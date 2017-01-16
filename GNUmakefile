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

all :: p1 l2

.PHONY: p1 l2
p1 : ProblemSet1.pdf

l2: convexOptimizationLecture2.pdf
convexOptimizationLecture2.pdf : jacobianAndHessian.tex quadraticFormGradient.tex

ProblemSet1.pdf :: ProblemSet1Problem8.tex ProblemSet1Problem7.tex ProblemSet1Problem6.tex ProblemSet1Problem5.tex ProblemSet1Problem4.tex ProblemSet1Problem3.tex ProblemSet1Problem2.tex ProblemSet1Problem1.tex

#all :: convexL1.pdf

#julia.tex : ../julia/METADATA
#mathematica.tex : ../mathematica/METADATA
#matlab.tex : ../matlab/METADATA
