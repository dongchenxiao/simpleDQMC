# first delete all default suffixes
.SUFFIXES:
# then add your suffixes
.SUFFIXES: .f90 .F90 .o

include ./make.sys

default: all

modu1 = mod_global.o matrix_tmp.o obser.o
modu2 = ftdqmc_core.o
dqmcf1 = mmthl.o mmthlm1.o mmthr.o mmthrm1.o mmuul.o mmuulm1.o mmuur.o mmuurm1.o \
         upgradeu.o sli.o salph.o sthop.o ftdqmc_initial.o inconfc.o outconfc.o \
         preq.o prtau.o
main = ftdqmc_main.o

objects = $(modu1) $(modu2) $(dqmcf1) $(main)

all: ftdqmc

ftdqmc: $(objects)
	$(LINKER) $(objects) -o ftdqmc $(LFLAGS) $(LIBS)

.f90.o:
	$(F90) $(FFLAGS) $*.f90

.F90.o:
	$(F90) $(FFLAGS) $*.F90

clean:
	rm -f *.mod
	rm -f *.o
	rm -f ftdqmc

clean-dat:
	rm -f *.dat
	rm -f *.bin.*
	rm -f *.out

clean-all: clean clean-dat
