obj =  module.o aux.o symmetry.o readHmnR.o inverse.o\
       eigen.o ham_qlayer2qlayer.o psi.o \
		 ham_slab.o ek_slab.o ek_bulk_polar.o ek_bulk2D.o \
       readinput.o fermisurface.o surfgreen.o surfstat.o \
		 mat_mul.o ham_ribbon.o ek_ribbon.o ham_bulk.o ek_bulk.o \
       fermiarc.o spintexture.o berrycurvature.o \
		 wanniercenter.o dos.o  \
		 landau_level.o berry.o \
       main.o

# compiler
f90  = mpif90 # -check all -pg -traceback

#FLAGS =  -O3 -nogen-interface  -warn all 
flag = -O3 -nogen-interface  -warn all 

# blas and lapack libraries
libs = -L/opt/intel/mkl/lib/ \
		-lmkl_intel_lp64 -lmkl_sequential \
		-lmkl_core -liomp5
 
main :  $(obj)
	$(f90) $(obj) -o wann_tools $(libs) 
	cp -f wann_tools ../bin

.SUFFIXES: .o .f90

.f90.o :
	$(f90) -c $(flag) $(includes) $*.f90

clean :
	rm -f *.o *.mod *~ wann_tools
