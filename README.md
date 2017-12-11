# lab15

$ cpplint main.cpp
#### Done processing main.cpp

$ cppcheck main.cpp
#### Checking main.cpp...

$ oclint main.cpp -- -c


#### OCLint Report

#### Summary: TotalFiles=1 FilesWithViolations=0 P1=0 P2=0 P3=0 


#### [OCLint (http://oclint.org) v0.11.1]

$ valgrind ./main
==97689== Memcheck, a memory error detector
==97689== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==97689== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==97689== Command: ./main
==97689== 
--97689-- run: /usr/bin/dsymutil "./main"
warning: no debug symbols in executable (-arch x86_64)
==97689== Syscall param msg->desc.port.name points to uninitialised byte(s)
==97689==    at 0x10049134A: mach_msg_trap (in /usr/lib/system/libsystem_kernel.dylib)
==97689==    by 0x100490796: mach_msg (in /usr/lib/system/libsystem_kernel.dylib)
==97689==    by 0x10048A485: task_set_special_port (in /usr/lib/system/libsystem_kernel.dylib)
==97689==    by 0x10062610E: _os_trace_create_debug_control_port (in /usr/lib/system/libsystem_trace.dylib)
==97689==    by 0x100626458: _libtrace_init (in /usr/lib/system/libsystem_trace.dylib)
==97689==    by 0x1001569DF: libSystem_initializer (in /usr/lib/libSystem.B.dylib)
==97689==    by 0x100019A1A: ImageLoaderMachO::doModInitFunctions(ImageLoader::LinkContext const&) (in /usr/lib/dyld)
==97689==    by 0x100019C1D: ImageLoaderMachO::doInitialization(ImageLoader::LinkContext const&) (in /usr/lib/dyld)
==97689==    by 0x1000154A9: ImageLoader::recursiveInitialization(ImageLoader::LinkContext const&, unsigned int, char const*, ImageLoader::InitializerTimingList&, ImageLoader::UninitedUpwards&) (in /usr/lib/dyld)
==97689==    by 0x100015440: ImageLoader::recursiveInitialization(ImageLoader::LinkContext const&, unsigned int, char const*, ImageLoader::InitializerTimingList&, ImageLoader::UninitedUpwards&) (in /usr/lib/dyld)
==97689==    by 0x100014523: ImageLoader::processInitializers(ImageLoader::LinkContext const&, unsigned int, ImageLoader::InitializerTimingList&, ImageLoader::UninitedUpwards&) (in /usr/lib/dyld)
==97689==    by 0x1000145B8: ImageLoader::runInitializers(ImageLoader::LinkContext const&, ImageLoader::InitializerTimingList&) (in /usr/lib/dyld)
==97689==  Address 0x10488cbac is on thread 1's stack
==97689==  in frame #2, created by task_set_special_port (???:)
==97689== 
Hello, World!
==97689== 
==97689== HEAP SUMMARY:
==97689==     in use at exit: 22,110 bytes in 160 blocks
==97689==   total heap usage: 176 allocs, 16 frees, 28,254 bytes allocated
==97689== 
==97689== LEAK SUMMARY:
==97689==    definitely lost: 0 bytes in 0 blocks
==97689==    indirectly lost: 0 bytes in 0 blocks
==97689==      possibly lost: 72 bytes in 3 blocks
==97689==    still reachable: 4,296 bytes in 7 blocks
==97689==         suppressed: 17,742 bytes in 150 blocks
==97689== Rerun with --leak-check=full to see details of leaked memory
==97689== 
==97689== For counts of detected and suppressed errors, rerun with: -v
==97689== Use --track-origins=yes to see where uninitialised values come from
==97689== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 4 from 4)
