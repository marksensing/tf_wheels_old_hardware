# Info: 

I'm learning tensorflow in class, and I had an old machine with a better processor than my laptop.
This machine doesn't support AVX instructions, in class we use TF 1.9, but AVX support is baked into the binaries after 1.6. 

As a result I ended up compiling tf on that machine to make sure I had a version that was compatable and thought I ought to share it.


My specs: 

Architecture:        x86_64 <br/>
CPU op-mode(s):      32-bit, 64-bit <br/>
Byte Order:          Little Endian<br/>
CPU(s):              4<br/>
On-line CPU(s) list: 0-3<br/>
Thread(s) per core:  1<br/>
Core(s) per socket:  4<br/>
Socket(s):           1<br/>
NUMA node(s):        1<br/>
Vendor ID:           GenuineIntel<br/>
CPU family:          6<br/>
Model:               26<br/>
Model name:          Intel(R) Xeon(R) CPU           W3580  @ 3.33GHz<br/>
Stepping:            5<br/>
CPU MHz:             1640.898
CPU max MHz:         3326.0000
CPU min MHz:         1596.0000
BogoMIPS:            6666.54
Virtualization:      VT-x
L1d cache:           32K
L1i cache:           32K
L2 cache:            256K
L3 cache:            8192K
NUMA node0 CPU(s):   0-3
Flags:               fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm dca sse4_1 sse4_2 popcnt lahf_lm pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid dtherm ida flush_l1d


