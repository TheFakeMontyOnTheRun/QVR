# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_C_STANDARD 90)

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.

add_library( # Sets the name of the library.
        qvr

        # Sets the library as a shared library.
        SHARED

        # Provides a relative path to your source file(s).
	bih.c 
	cap_avi.c 
	cap_ogg.c 
	cd_shared.c
	crypto.c
	cl_collision.c
	cl_demo.c
	cl_dyntexture.c
	cl_input.c
	cl_main.c
	cl_parse.c
	cl_particles.c
	cl_screen.c
	cl_video.c
	clvm_cmds.c
	cmd.c
	collision.c
	common.c
	console.c
	csprogs.c
	curves.c
	cvar.c
	dpsoftrast.c
	dpvsimpledecode.c
	filematch.c
	fractalnoise.c
	fs.c
	ft2.c
	utf8lib.c
	gl_backend.c
	gl_draw.c
	gl_rmain.c
	gl_rsurf.c
	gl_textures.c
	hmac.c
	host.c
	host_cmd.c
	image.c
	image_png.c
	jpeg.c
	keys.c
	lhnet.c
	libcurl.c
	mathlib.c
	matrixlib.c
	mdfour.c
	menu.c
	meshqueue.c
	mod_skeletal_animatevertices_sse.c
	mod_skeletal_animatevertices_generic.c
	model_alias.c
	model_brush.c
	model_shared.c
	model_sprite.c
	mvm_cmds.c
	netconn.c
	palette.c
	polygon.c
	portals.c
	protocol.c
	prvm_cmds.c
	prvm_edict.c
	prvm_exec.c
	r_explosion.c
	r_lerpanim.c
	r_lightning.c
	r_modules.c
	r_shadow.c
	r_sky.c
	r_sprites.c
	sbar.c
	snprintf.c
	sv_demo.c
	sv_main.c
	sv_move.c
	sv_phys.c
	sv_user.c
	svbsp.c
	svvm_cmds.c
	sys_shared.c
	vid_shared.c
	view.c
	wad.c
	world.c
	zone.c
	snd_main.c snd_mem.c snd_mix.c snd_ogg.c snd_wav.c snd_modplug.c
	cd_null.c
	builddate.c sys_linux.c vid_android.c thread_pthread.c snd_android.c
	QVR.c
)

# Searches for a specified prebuilt library and stores the path as a
# variable. Because CMake includes system libraries in the search path by
# default, you only need to specify the name of the public NDK library
# you want to add. CMake verifies that the library exists before
# completing its build.

find_library( # Sets the name of the path variable.
        log-lib

        # Specifies the name of the NDK library that
        # you want CMake to locate.
        log)

find_library( # Sets the name of the path variable.
        android-lib

        # Specifies the name of the NDK library that
        # you want CMake to locate.
        android)


# Specifies libraries CMake should link to your target library. You
# can link multiple libraries, such as libraries you define in this
# build script, prebuilt third-party libraries, or system libraries.

target_link_libraries( # Specifies the target library.
        qvr
        ${android-lib}

        android
        jnigraphics
        EGL
        OpenSLES
        GLESv2

        # Links the target library to the log library
        # included in the NDK.
        ${log-lib})
