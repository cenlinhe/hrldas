# Makefile 
#
.SUFFIXES:
.SUFFIXES: .o .F

include ../user_build_options

OBJS = \
	module_date_utilities.o \
	module_model_constants.o \
	module_ra_gfdleta.o \
        module_wrf_error.o \
	module_wrf_utilities.o \
	kwm_string_utilities.o \
        module_domain.o
	
CPPHRLDAS = -D_HRLDAS_OFFLINE_


all:	$(OBJS)

.F.o:
	@echo ""
	$(RM) $(*).f90
	$(CPP) $(CPPFLAGS) $(CPPHRLDAS) $(*).F > $(*).f90
	$(COMPILERF90) -o $(@) -c $(F90FLAGS) $(FREESOURCE) $(*).f90
	@echo ""

#
# Dependencies:
#

#
# This command cleans up object (etc.) files:
#

clean:
	$(RM) *.o *.mod *.stb *~ *.f90

