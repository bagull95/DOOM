################################################################
#
# $Id:$
#
# $Log:$
#

gcc:	CC=  gcc
gcc:	CFLAGS=-m32 -g -DNORMALUNIX -DLINUX
gcc:	all
clang:	CC=  clang
clang:	CFLAGS=-m32 -g -DNORMALUNIX -DLINUX
clang:	all
icc:	CC=  /opt/intel/compilers_and_libraries_2018.1.163/linux/bin/intel64/icc
icc:	CFLAGS=-m32 -g  -DNORMALUNIX -DLINUX
icc:	all
zapcc:	CC = ../../zapcc-20170802-175507/bin/zapcc
zapcc:	CFLAGS=-m32 -g -DNORMALUNIX -DLINUX
zapcc:	all

#CFLAGS=-m32 -g -Wall -DNORMALUNIX -DLINUX  # -DUSEASM 
LDFLAGS=-L/usr/lib32 -L/usr/lib/i386-linux-gnu/ #-L/usr/X11R6/lib
LIBS=-lnsl -lm -lc -lXext -lX11

# subdirectory for objects
O=linux

# not too sophisticated dependency
OBJS=				\
		$(O)/doomdef.o		\
		$(O)/doomstat.o		\
		$(O)/dstrings.o		\
		$(O)/i_system.o		\
		$(O)/i_sound.o		\
		$(O)/i_video.o		\
		$(O)/i_net.o			\
		$(O)/tables.o			\
		$(O)/f_finale.o		\
		$(O)/f_wipe.o 		\
		$(O)/d_main.o			\
		$(O)/d_net.o			\
		$(O)/d_items.o		\
		$(O)/g_game.o			\
		$(O)/m_menu.o			\
		$(O)/m_misc.o			\
		$(O)/m_argv.o  		\
		$(O)/m_bbox.o			\
		$(O)/m_fixed.o		\
		$(O)/m_swap.o			\
		$(O)/m_cheat.o		\
		$(O)/m_random.o		\
		$(O)/am_map.o			\
		$(O)/p_ceilng.o		\
		$(O)/p_doors.o		\
		$(O)/p_enemy.o		\
		$(O)/p_floor.o		\
		$(O)/p_inter.o		\
		$(O)/p_lights.o		\
		$(O)/p_map.o			\
		$(O)/p_maputl.o		\
		$(O)/p_plats.o		\
		$(O)/p_pspr.o			\
		$(O)/p_setup.o		\
		$(O)/p_sight.o		\
		$(O)/p_spec.o			\
		$(O)/p_switch.o		\
		$(O)/p_mobj.o			\
		$(O)/p_telept.o		\
		$(O)/p_tick.o			\
		$(O)/p_saveg.o		\
		$(O)/p_user.o			\
		$(O)/r_bsp.o			\
		$(O)/r_data.o			\
		$(O)/r_draw.o			\
		$(O)/r_main.o			\
		$(O)/r_plane.o		\
		$(O)/r_segs.o			\
		$(O)/r_sky.o			\
		$(O)/r_things.o		\
		$(O)/w_wad.o			\
		$(O)/wi_stuff.o		\
		$(O)/v_video.o		\
		$(O)/st_lib.o			\
		$(O)/st_stuff.o		\
		$(O)/hu_stuff.o		\
		$(O)/hu_lib.o			\
		$(O)/s_sound.o		\
		$(O)/z_zone.o			\
		$(O)/info.o				\
		$(O)/sounds.o

all:	 $(O)/linuxxdoom

clean:
	rm -f *.o *~ *.flc
	rm -f linux/*

$(O)/linuxxdoom:	$(OBJS) $(O)/i_main.o
	$(CC) $(CFLAGS) $(OBJS) $(O)/i_main.o \
	-o $(O)/linuxxdoom $(LDFLAGS) $(LIBS)

$(O)/%.o:	%.c
	$(CC) $(CFLAGS) -c $< -o $@

#############################################################
#
#############################################################
