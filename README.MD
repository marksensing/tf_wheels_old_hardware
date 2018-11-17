# Info: 

I'm learning tensorflow in class, and I had an old machine with a better processor than my laptop.
This machine doesn't support AVX instructions, in class we use TF 1.9, but AVX support is baked into the binaries after 1.6. 

As a result I ended up compiling tf on that machine to make sure I had a version that was compatable and thought I ought to share it.


# My specs: 

## If your setup is close to this, this whl may work for your use case as well. 

## OS 
No LSB modules are available. <br />
Distributor ID:	Ubuntu <br />
Description:	Ubuntu 18.04.1 LTS <br />
Release:	18.04 <br />
Codename:	bionic <br />

<br />
## CPU
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
CPU MHz:             1640.898<br/>
CPU max MHz:         3326.0000<br/>
CPU min MHz:         1596.0000<br/>
BogoMIPS:            6666.54<br/>
Virtualization:      VT-x<br/>
L1d cache:           32K<br/>
L1i cache:           32K<br/>
L2 cache:            256K<br/>
L3 cache:            8192K<br/>
NUMA node0 CPU(s):   0-3<br/>
Flags:               fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm dca sse4_1 sse4_2 popcnt lahf_lm pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid dtherm ida flush_l1d

<br />

# Other stuff about running tf on old hardware: 

<br />
My old computer also happens to have a graphics card. (nvidia quadro fx 3800)
Note that official tf build supports compute capability 3.5 and higher. 
My card is 1.3, so not a candadate for running tf. 
<br/>
The compute capability of a (more modern) card can be checked here: 
https://developer.nvidia.com/cuda-gpus
<br/>
For older cards (like mine) see: 
https://developer.nvidia.com/cuda-legacy-gpus 
<br/>

# A question I had, and found the answer to:

<br/>

## If you can compile TF for older CPUs can I compile it for an older gpu (with compute capability < 3.0)?

### TL;DR: No. The libs that TF uses under the hood make this impossible. 

<br/>

### Long answer:

Tensorflow uses an Nvidia lib called cuDNN to take advantage of a GPU. (See https://developer.nvidia.com/cudnn). One of the first steps in installing the GPU version of tensorflow is getting this lib. The problem is that this lib requires compute capability 3.0 or higher. Since TF was written using cuDNN, you're going to need a new card. 
