################################### LICENCE BEGIN ###############################
# GEM-MACH - Atmospheric chemistry library for the GEM numerical atmospheric model
# Copyright (C) 2007-2013 - Air Quality Research Division &
#                           National Prediction Operations division
#                           Environnement Canada
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2.1 of the License, or (at your option) any later version.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this library; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301  USA
################################### LICENCE END #################################

SHELL = /bin/sh

INCLUDE_DIR=../lib/$(ARCH)
FC          = s.compile
FFLAGS_sles-11-broadwell-64-xc40 = -O 2   -librmn -openmp -includes $(INCLUDE_DIR) -optf="-fp-model source -g"
FFLAGS_Linux_x86-64 =  -O 2   -librmn -openmp -includes $(INCLUDE_DIR) -optf="-fp-model source "
# -warn all -traceback -check all -check uninit
FFLAGS_DEBUG_sles-11-broadwell-64-xc40 = -O 0 -debug -librmn -openmp -includes $(INCLUDE_DIR) -optf="-fp-model source -DDEBUG"
FFLAGS_DEBUG_Linux_x86-64 = -O 0 -debug -librmn -openmp -includes $(INCLUDE_DIR) -optf="-fp-model source -warn all "

NBJOBS_sles-11-broadwell-64-xc40 = 8
NBJOBS_Linux_x86-64 = 8


LIBNAME     = libgemmach.a
LIBARCHIVE  = ../lib/$(EC_ARCH)


.PHONY: clean distclean debug

.SUFFIXES: $(SUFFIXES) .ftn90

# Modules and interface: must be compiled first!
# Also, chm_utils_mod must be compiled first in the modules, since it is included by some other modules
.FMODULES = 	chm_utils_mod.ftn90 \
		chm_ptopo_grid_mod.ftn90 \
		chm_metvar_mod.ftn90 \
		chm_headers_mod.ftn90 \
		chm_nml_mod.ftn90 \
		chm_consphychm_mod.ftn90 \
		chm_species_info_mod.ftn90 \
		chm_species_idx_mod.ftn90 \
		chm_mjrpts_sortinfo_mod.ftn90 \
		chm_datime_mod.ftn90 \
		chm_phyvar_mod.ftn90 \
		linoz_mod.ftn90 \
		mach_cam_utils_mod.ftn90 \
		mach_aurams_headers_mod.ftn90 \
		mach_headers_mod.ftn90 \
		mach_pkg_adom2_mod.ftn90 \
		mach_pkg_cam2bins_mod.ftn90 \
		mach_pkg_cam12bins_mod.ftn90 \
		mach_pkg_diag_mod.ftn90 \
		mach_pkg_misc_mod.ftn90 \
		mach_pkg_debug_mod.ftn90 \
		mach_pkg_tendencies_mod.ftn90 \
		mach_gas_chemicbi_mod.ftn90 \
		mach_cam_pre_mod.ftn90 \
		mach_cam_headers_mod.ftn90 \
		mach_incld_mod.ftn90 \
		mach_incld_headers_mod.ftn90 \
		mach_hetv_headers_mod.ftn90 \
		mach_gas_drydep_mod.ftn90 \
		mach_gas_headers_mod.ftn90  \
		mach_pkg_linoz_mod.ftn90 \
		mach_linoz_headers_mod.ftn90 


.FFILES = 	chm_businit.ftn90 \
		chm_chk_met_dgb.ftn90 \
		chm_chk_mjpt_dbg.ftn90 \
		chm_chk_pm_dbg.ftn90 \
		chm_chk_tendencies.ftn90 \
		chm_diffusion.ftn90 \
		chm_dupl_tracr_lev.ftn90 \
		chm_exe.ftn90 \
		chm_fst_closefile.ftn90 \
		chm_fst_openfile.ftn90 \
		chm_geopot.ftn90 \
		chm_getphybus_struct.ftn90 \
		chm_gz_int.ftn90 \
		chm_load_emissions.ftn90 \
		chm_load_metvar.ftn90 \
		chm_mjrpts_get_emissions.ftn90 \
		chm_mjrpts_get_size.ftn90 \
		chm_mjrpts_get_stkinfo.ftn90 \
		chm_nml.ftn90 \
		chm_pkg_fields_init.ftn90 \
		chm_plumerise_prep_emiss.ftn90 \
		chm_stop.ftn90 \
		gocart_so2so4.ftn90 \
		linoz_litcoeff.ftn90 \
		linoz_main.ftn90 \
		linoz_tend.ftn90 \
		mach_aurams_cldcv2d.ftn90 \
		mach_aurams_cwc_per_bin.ftn90 \
		mach_aurams_prntrow.ftn90 \
		mach_aurams_tsysms.ftn90 \
		mach_biog_emissions.ftn90 \
		mach_biog_main.ftn90 \
		mach_biog_parcalc.ftn90 \
		mach_calc_diag.ftn90 \
		mach_calc_season.ftn90 \
		mach_cam_aeroact.ftn90 \
		mach_cam_aerocld.ftn90 \
		mach_cam_aeroprop.ftn90 \
		mach_cam_cas.ftn90 \
		mach_pm_chem.ftn90 \
		mach_cam_coagd.ftn90 \
		mach_cam_condsoa.ftn90 \
		mach_cam_drydepo.ftn90 \
		mach_cam_drypar.ftn90 \
		mach_cam_flux.ftn90 \
		mach_cam_intrsec_inner.ftn90 \
		mach_cam_intrsec1_inner.ftn90 \
		mach_cam_intrsec1_outer.ftn90 \
		mach_cam_intrsec_outer.ftn90 \
		mach_cam_pre.ftn90 \
		mach_cam_rain.ftn90 \
		mach_cam_scaveng.ftn90 \
		mach_cam_sfss.ftn90 \
		mach_cam_sulfate.ftn90 \
		mach_cam_tenddist.ftn90 \
		mach_cam_main.ftn90 \
		mach_diff_boundary.ftn90 \
		mach_diff_flux.ftn90 \
		mach_diff_rpnphy.ftn90 \
		mach_diffusion.ftn90 \
		mach_fugitive_dust.ftn90 \
		mach_gas_chemi.ftn90 \
		mach_gas_drive.ftn90 \
		mach_gas_drydep_main.ftn90 \
		mach_gas_drydep_ra.ftn90 \
		mach_gas_drydep_ra2.ftn90 \
		mach_gas_drydep_solver.ftn90 \
		mach_gas_drydep_solver2.ftn90 \
		mach_gas_drydep_stat.ftn90 \
		mach_gas_jcorr.ftn90 \
		mach_gas_main.ftn90 \
		mach_gas_soa_yield.ftn90 \
		mach_gas_strato.ftn90 \
		mach_gas_uprate.ftn90 \
		mach_hetv_activity.ftn90 \
		mach_hetv_activity_single.ftn90 \
		mach_hetv_case1.ftn90 \
		mach_hetv_case10.ftn90 \
		mach_hetv_case11.ftn90 \
		mach_hetv_case12.ftn90 \
		mach_hetv_case12_single.ftn90 \
		mach_hetv_case2.ftn90 \
		mach_hetv_case2_single.ftn90 \
		mach_hetv_case3.ftn90 \
		mach_hetv_case4.ftn90 \
		mach_hetv_case5.ftn90 \
		mach_hetv_case6.ftn90 \
		mach_hetv_case7.ftn90 \
		mach_hetv_case8.ftn90 \
		mach_hetv_case9.ftn90 \
		mach_hetv_case9_single.ftn90 \
		mach_hetv_corrhno3.ftn90 \
		mach_hetv_corrhno3_single.ftn90 \
		mach_hetv_hetchem.ftn90 \
		mach_hetv_hetvcall.ftn90 \
		mach_hetv_main.ftn90 \
		mach_hetv_main_single.ftn90 \
		mach_hetv_poly3v.ftn90 \
		mach_hetv_rebin.ftn90 \
		mach_hetv_water.ftn90 \
		mach_hetv_water_single.ftn90 \
		mach_incld_concmp.ftn90 \
		mach_incld_diffun.ftn90 \
		mach_incld_dochem.ftn90 \
		mach_incld_fff.ftn90 \
		mach_incld_findh.ftn90 \
		mach_incld_fn_dtnew.ftn90 \
		mach_incld_funeq.ftn90 \
		mach_incld_main.ftn90 \
		mach_incld_intrqf.ftn90 \
		mach_incld_intsca_il.ftn90 \
		mach_incld_rates.ftn90 \
		mach_incld_shift3d_aero.ftn90 \
		mach_incld_soleq.ftn90 \
		mach_incld_steady.ftn90 \
		mach_incld_steady1.ftn90 \
		mach_incld_upaqr.ftn90 \
		mach_incld_upaqr1.ftn90 \
		mach_incld_upaqr2.ftn90 \
		mach_input_check.ftn90 \
		mach_landuse.ftn90 \
		mach_linoz_interp.ftn90 \
		mach_linoz_xcol.ftn90 \
		mach_main.ftn90 \
		mach_output.ftn90 \
		mach_plumerise.ftn90 \
		mach_plumerise_apply.ftn90 \
		mach_plumerise_weight.ftn90 \
		mach_plumerise_weight4fire.ftn90 \
		chm_mjrpts_get_plmriseinfo.ftn90 \
		mach_pressure.ftn90 \
		mach_strato_tend.ftn90 \
		mach_strato_xcol.ftn90 \
		mach_tridiag.ftn90 


.OFILES  = $(.FFILES:.ftn90=.o)

.OMODULES = $(.FMODULES:.ftn90=.o)

.ftn90.o:
	@echo "Compilation de $(<)"
	$(FC) $(FFLAGS_$(DEBUG)$(BASE_ARCH)) $(TENDENCIES) -src $<

all: ${.OMODULES} $(.OFILES)
	@echo "Target all"
	$(MAKE) library

fast:
	@echo "Target fast"
	$(MAKE) $(MAKEFLAGS) $(.OMODULES)
	$(MAKE) $(MAKEFLAGS) -k -j $(NBJOBS_$(BASE_ARCH)) $(.OFILES)
	$(MAKE) library

debugfast:
	@echo "Target debugfast"
	$(MAKE) $(MAKEFLAGS) $(.OMODULES)
	$(MAKE) $(MAKEFLAGS) -k -j $(NBJOBS_$(BASE_ARCH)) DEBUG=DEBUG_ $(.OFILES)
	$(MAKE) library

debug:
	@echo "Target debug"
	$(MAKE) $(MAKEFLAGS) DEBUG=DEBUG_ all

tendencies:
	$(MAKE) $(MAKEFLAGS) TENDENCIES='-defines="-DMACH_TENDENCIES"' all

library:
	@echo "Target library"
	ar rv $(LIBNAME) ${.OMODULES} $(.OFILES); \
	mkdir -p $(LIBARCHIVE); \
	cp  $(LIBNAME) $(LIBARCHIVE); \
	cp  *.mod $(LIBARCHIVE);

stub: chm_stubs.o
	@echo "Target stub"
	ar rv libchmstubs.a chm_stubs.o; \
	cp libchmstubs.a $(LIBARCHIVE)

distclean: clean
	@echo "Target distclean"
	rm -fr *~ *.a $(LIBARCHIVE)/*.a $(LIBARCHIVE)/*.mod

clean:
	@echo "Target clean"
	rm -fr *.o *.f90 .fo gmon.out $(MOD)*.c $(MOD)*.o *.mod rii_files
