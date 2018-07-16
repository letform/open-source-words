deno a secure typescript runtime built on v8 supports typescript 2 8 out of the box uses v8 6 8 275 3 that is its very modern javascript no package json no npm not explicitly compatible with node imports reference source code urls only import test from https unpkg com deno testing 0 0 5 testing ts import log from util ts remote code is fetched and cached on first execution and never updated until the code is run with the reload flag so this will still work on an airplane see deno src for details on the cache file system and network access can be controlled in order to run sandboxed code defaults to read only file system access and no network access access between v8 unprivileged and golang privileged is only done via serialized messages defined in this protobuf this makes it easy to audit to enable write access explicitly use allow write and allow net for network access single executable ls lh deno rwxrwxr x 1 ryan ryan 55m may 28 23 46 deno ldd deno linux vdso so 1 0x00007ffc6797a000 libpthread so 0 lib x86 64 linux gnu libpthread so 0 0x00007f104fa47000 libstdc so 6 usr lib x86 64 linux gnu libstdc so 6 0x00007f104f6c5000 libm so 6 lib x86 64 linux gnu libm so 6 0x00007f104f3bc000 libgcc s so 1 lib x86 64 linux gnu libgcc s so 1 0x00007f104f1a6000 libc so 6 lib x86 64 linux gnu libc so 6 0x00007f104eddc000 lib64 ld linux x86 64 so 2 0x00007f104fc64000 always dies on uncaught errors supports top level await aims to be browser compatible status segfaulty check back soon roadmap is here also see this presentation http tinyclouds org jsconf2018 pdf github noise i am excited about all the interest in this project however do understand that this is very much a non functional prototype theres a huge amount of heavy lifting to do unless you are participating in that please maintain radio silence on github this includes submitting trivial prs like improving readme build instructions compile instructions get depot tools and make sure its in your path you need yarn installed you need rust installed you might want ccache installed fetch the third party dependencies tools build third party py generate ninja files gn gen out default gn gen out release args cc wrapper ccache is official build true gn gen out debug args cc wrapper ccache is debug true then build with ninja will take a while to complete ninja c out debug deno other useful commands gn args out debug list gn args out debug gn desc out debug deno gn help