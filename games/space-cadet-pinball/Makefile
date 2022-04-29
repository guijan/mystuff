COMMENT 	 = decompilation of 3D Pinball for Windows - Space Cadet
V		 = 2.0.1
PKGNAME		 = space-cadet-pinball-${V}

GH_ACCOUNT	 = k4zmu2a
GH_PROJECT	 = SpaceCadetPinball
GH_TAGNAME	 = Release_${V}

CATEGORIES	 = games

# The engine is MIT, the (not included) assets are proprietary and included
# with Windows 95 through XP.
PERMIT_PACKAGE	 = Yes

WANTLIB		+= pthread SDL2 SDL2_mixer m ${COMPILER_LIBCXX} c

# C++11
COMPILER	 = base-clang ports-gcc

MODULES 	 = devel/cmake

LIB_DEPENDS	 = devel/sdl2 devel/sdl2-mixer
RUN_DEPENDS	 = x11/gtk+3,-guic \
		   devel/desktop-file-utils \
		   audio/timidity # Needed to play the MIDI background music.

# Remove the CONFIGURE_ARGS line below if
# https://github.com/k4zmu2a/SpaceCadetPinball/pull/136 is merged.
CONFIGURE_ARGS	 = -DCMAKE_CXX_FLAGS="-I${X11BASE}/include ${CXXFLAGS}"

# Install an empty directory so the user can place the game assets
# in it by hand later.
post-install:
	mkdir -p ${PREFIX}/share/SpaceCadetPinball

.include <bsd.port.mk>
