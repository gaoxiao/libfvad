cmake_minimum_required(VERSION 3.14)
project(libfvad C)

set(CMAKE_C_STANDARD 11)

include_directories(include)
include_directories(src)
include_directories(src/signal_processing)
include_directories(src/vad)
include_directories(tests)

add_executable(libfvad
        examples/fvadwav.c
        include/fvad.h
        src/signal_processing/division_operations.c
        src/signal_processing/energy.c
        src/signal_processing/get_scaling_square.c
        src/signal_processing/resample_48khz.c
        src/signal_processing/resample_by_2_internal.c
        src/signal_processing/resample_by_2_internal.h
        src/signal_processing/resample_fractional.c
        src/signal_processing/signal_processing_library.h
        src/signal_processing/spl_inl.c
        src/signal_processing/spl_inl.h
        src/vad/vad_core.c
        src/vad/vad_core.h
        src/vad/vad_filterbank.c
        src/vad/vad_filterbank.h
        src/vad/vad_gmm.c
        src/vad/vad_gmm.h
        src/vad/vad_sp.c
        src/vad/vad_sp.h
        src/common.h
        src/fvad.c)
target_link_libraries(libfvad
        sndfile)