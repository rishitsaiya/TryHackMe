## Reverse it or read it?
The main idea finding the flag is just using Radar2/IDA to reverse it.

#### Step-1:
After downloading, `hello.hello`, I had 2 paths to explore. Luckily both gave answer easily.

#### Step-2:
I tried using Radar2 to reverse it by `r2 hello.hello`

This was my procedure to get to flag:

```
[0x00001060]> aaa
[x] Analyze all flags starting with sym. and entry0 (aa)
[x] Analyze function calls (aac)
[x] Analyze len bytes of instructions for references (aar)
[x] Constructing a function name for fcn.* and sym.func.* functions (aan)
[x] Type matching analysis for all functions (aaft)
[x] Use -AA or aaaa to perform additional experimental analysis.
[0x00001060]> afl
0x00001000    3 23           sym._init
0x00001030    1 6            sym.imp.puts
0x00001040    1 6            sym.imp.printf
0x00001050    1 6            sub.__cxa_finalize_1050
0x00001060    1 43           entry0
0x00001090    4 41   -> 34   sym.deregister_tm_clones
0x000010c0    4 57   -> 51   sym.register_tm_clones
0x00001100    5 57   -> 50   sym.__do_global_dtors_aux
0x00001140    1 5            entry.init0
0x00001145    1 24           sym.skip
0x0000115d    1 23           sym.main
0x00001180    3 93   -> 84   sym.__libc_csu_init
0x000011e0    1 1            sym.__libc_csu_fini
0x000011e4    1 9            sym._fini
[0x00001060]> pdf @sym.skip
/ (fcn) sym.skip 24
|   sym.skip ();
|           0x00001145      55             push rbp
|           0x00001146      4889e5         mov rbp, rsp
|           0x00001149      488d3db80e00.  lea rdi, qword str.THM_345y_f1nd_345y_60 ; 0x2008 ; "THM{345y_f1nd_345y_60}" ; const char *format
|           0x00001150      b800000000     mov eax, 0
|           0x00001155      e8e6feffff     call sym.imp.printf         ; int printf(const char *format)
|           0x0000115a      90             nop
|           0x0000115b      5d             pop rbp
\           0x0000115c      c3             ret
[0x00001060]> q
```
<center>
<strong>OR</strong>
</center>

#### Step-2:
I just used directly IDA to get the flag. Open `hello.hello` IDA by `ida64` and then just explore the instructions.

<img src="Flag,png">


#### Step-3:
Finally the flag becomes:
`THM{345y_f1nd_345y_60}`