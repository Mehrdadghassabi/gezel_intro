                                      1 ;--------------------------------------------------------
                                      2 ; File Created by SDCC : free open source ANSI-C Compiler
                                      3 ; Version 4.0.0 #11528 (Linux)
                                      4 ;--------------------------------------------------------
                                      5 	.module sort
                                      6 	.optsdcc -mmcs51 --model-small
                                      7 	
                                      8 ;--------------------------------------------------------
                                      9 ; Public variables in this module
                                     10 ;--------------------------------------------------------
                                     11 	.globl _send_PARM_2
                                     12 	.globl _main
                                     13 	.globl _terminate
                                     14 	.globl _send
                                     15 	.globl _CY
                                     16 	.globl _AC
                                     17 	.globl _F0
                                     18 	.globl _RS1
                                     19 	.globl _RS0
                                     20 	.globl _OV
                                     21 	.globl _F1
                                     22 	.globl _P
                                     23 	.globl _PS
                                     24 	.globl _PT1
                                     25 	.globl _PX1
                                     26 	.globl _PT0
                                     27 	.globl _PX0
                                     28 	.globl _RD
                                     29 	.globl _WR
                                     30 	.globl _T1
                                     31 	.globl _T0
                                     32 	.globl _INT1
                                     33 	.globl _INT0
                                     34 	.globl _TXD
                                     35 	.globl _RXD
                                     36 	.globl _P3_7
                                     37 	.globl _P3_6
                                     38 	.globl _P3_5
                                     39 	.globl _P3_4
                                     40 	.globl _P3_3
                                     41 	.globl _P3_2
                                     42 	.globl _P3_1
                                     43 	.globl _P3_0
                                     44 	.globl _EA
                                     45 	.globl _ES
                                     46 	.globl _ET1
                                     47 	.globl _EX1
                                     48 	.globl _ET0
                                     49 	.globl _EX0
                                     50 	.globl _P2_7
                                     51 	.globl _P2_6
                                     52 	.globl _P2_5
                                     53 	.globl _P2_4
                                     54 	.globl _P2_3
                                     55 	.globl _P2_2
                                     56 	.globl _P2_1
                                     57 	.globl _P2_0
                                     58 	.globl _SM0
                                     59 	.globl _SM1
                                     60 	.globl _SM2
                                     61 	.globl _REN
                                     62 	.globl _TB8
                                     63 	.globl _RB8
                                     64 	.globl _TI
                                     65 	.globl _RI
                                     66 	.globl _P1_7
                                     67 	.globl _P1_6
                                     68 	.globl _P1_5
                                     69 	.globl _P1_4
                                     70 	.globl _P1_3
                                     71 	.globl _P1_2
                                     72 	.globl _P1_1
                                     73 	.globl _P1_0
                                     74 	.globl _TF1
                                     75 	.globl _TR1
                                     76 	.globl _TF0
                                     77 	.globl _TR0
                                     78 	.globl _IE1
                                     79 	.globl _IT1
                                     80 	.globl _IE0
                                     81 	.globl _IT0
                                     82 	.globl _P0_7
                                     83 	.globl _P0_6
                                     84 	.globl _P0_5
                                     85 	.globl _P0_4
                                     86 	.globl _P0_3
                                     87 	.globl _P0_2
                                     88 	.globl _P0_1
                                     89 	.globl _P0_0
                                     90 	.globl _B
                                     91 	.globl _ACC
                                     92 	.globl _PSW
                                     93 	.globl _IP
                                     94 	.globl _P3
                                     95 	.globl _IE
                                     96 	.globl _P2
                                     97 	.globl _SBUF
                                     98 	.globl _SCON
                                     99 	.globl _P1
                                    100 	.globl _TH1
                                    101 	.globl _TH0
                                    102 	.globl _TL1
                                    103 	.globl _TL0
                                    104 	.globl _TMOD
                                    105 	.globl _TCON
                                    106 	.globl _PCON
                                    107 	.globl _DPH
                                    108 	.globl _DPL
                                    109 	.globl _SP
                                    110 	.globl _P0
                                    111 ;--------------------------------------------------------
                                    112 ; special function registers
                                    113 ;--------------------------------------------------------
                                    114 	.area RSEG    (ABS,DATA)
      000000                        115 	.org 0x0000
                           000080   116 _P0	=	0x0080
                           000081   117 _SP	=	0x0081
                           000082   118 _DPL	=	0x0082
                           000083   119 _DPH	=	0x0083
                           000087   120 _PCON	=	0x0087
                           000088   121 _TCON	=	0x0088
                           000089   122 _TMOD	=	0x0089
                           00008A   123 _TL0	=	0x008a
                           00008B   124 _TL1	=	0x008b
                           00008C   125 _TH0	=	0x008c
                           00008D   126 _TH1	=	0x008d
                           000090   127 _P1	=	0x0090
                           000098   128 _SCON	=	0x0098
                           000099   129 _SBUF	=	0x0099
                           0000A0   130 _P2	=	0x00a0
                           0000A8   131 _IE	=	0x00a8
                           0000B0   132 _P3	=	0x00b0
                           0000B8   133 _IP	=	0x00b8
                           0000D0   134 _PSW	=	0x00d0
                           0000E0   135 _ACC	=	0x00e0
                           0000F0   136 _B	=	0x00f0
                                    137 ;--------------------------------------------------------
                                    138 ; special function bits
                                    139 ;--------------------------------------------------------
                                    140 	.area RSEG    (ABS,DATA)
      000000                        141 	.org 0x0000
                           000080   142 _P0_0	=	0x0080
                           000081   143 _P0_1	=	0x0081
                           000082   144 _P0_2	=	0x0082
                           000083   145 _P0_3	=	0x0083
                           000084   146 _P0_4	=	0x0084
                           000085   147 _P0_5	=	0x0085
                           000086   148 _P0_6	=	0x0086
                           000087   149 _P0_7	=	0x0087
                           000088   150 _IT0	=	0x0088
                           000089   151 _IE0	=	0x0089
                           00008A   152 _IT1	=	0x008a
                           00008B   153 _IE1	=	0x008b
                           00008C   154 _TR0	=	0x008c
                           00008D   155 _TF0	=	0x008d
                           00008E   156 _TR1	=	0x008e
                           00008F   157 _TF1	=	0x008f
                           000090   158 _P1_0	=	0x0090
                           000091   159 _P1_1	=	0x0091
                           000092   160 _P1_2	=	0x0092
                           000093   161 _P1_3	=	0x0093
                           000094   162 _P1_4	=	0x0094
                           000095   163 _P1_5	=	0x0095
                           000096   164 _P1_6	=	0x0096
                           000097   165 _P1_7	=	0x0097
                           000098   166 _RI	=	0x0098
                           000099   167 _TI	=	0x0099
                           00009A   168 _RB8	=	0x009a
                           00009B   169 _TB8	=	0x009b
                           00009C   170 _REN	=	0x009c
                           00009D   171 _SM2	=	0x009d
                           00009E   172 _SM1	=	0x009e
                           00009F   173 _SM0	=	0x009f
                           0000A0   174 _P2_0	=	0x00a0
                           0000A1   175 _P2_1	=	0x00a1
                           0000A2   176 _P2_2	=	0x00a2
                           0000A3   177 _P2_3	=	0x00a3
                           0000A4   178 _P2_4	=	0x00a4
                           0000A5   179 _P2_5	=	0x00a5
                           0000A6   180 _P2_6	=	0x00a6
                           0000A7   181 _P2_7	=	0x00a7
                           0000A8   182 _EX0	=	0x00a8
                           0000A9   183 _ET0	=	0x00a9
                           0000AA   184 _EX1	=	0x00aa
                           0000AB   185 _ET1	=	0x00ab
                           0000AC   186 _ES	=	0x00ac
                           0000AF   187 _EA	=	0x00af
                           0000B0   188 _P3_0	=	0x00b0
                           0000B1   189 _P3_1	=	0x00b1
                           0000B2   190 _P3_2	=	0x00b2
                           0000B3   191 _P3_3	=	0x00b3
                           0000B4   192 _P3_4	=	0x00b4
                           0000B5   193 _P3_5	=	0x00b5
                           0000B6   194 _P3_6	=	0x00b6
                           0000B7   195 _P3_7	=	0x00b7
                           0000B0   196 _RXD	=	0x00b0
                           0000B1   197 _TXD	=	0x00b1
                           0000B2   198 _INT0	=	0x00b2
                           0000B3   199 _INT1	=	0x00b3
                           0000B4   200 _T0	=	0x00b4
                           0000B5   201 _T1	=	0x00b5
                           0000B6   202 _WR	=	0x00b6
                           0000B7   203 _RD	=	0x00b7
                           0000B8   204 _PX0	=	0x00b8
                           0000B9   205 _PT0	=	0x00b9
                           0000BA   206 _PX1	=	0x00ba
                           0000BB   207 _PT1	=	0x00bb
                           0000BC   208 _PS	=	0x00bc
                           0000D0   209 _P	=	0x00d0
                           0000D1   210 _F1	=	0x00d1
                           0000D2   211 _OV	=	0x00d2
                           0000D3   212 _RS0	=	0x00d3
                           0000D4   213 _RS1	=	0x00d4
                           0000D5   214 _F0	=	0x00d5
                           0000D6   215 _AC	=	0x00d6
                           0000D7   216 _CY	=	0x00d7
                                    217 ;--------------------------------------------------------
                                    218 ; overlayable register banks
                                    219 ;--------------------------------------------------------
                                    220 	.area REG_BANK_0	(REL,OVR,DATA)
      000000                        221 	.ds 8
                                    222 ;--------------------------------------------------------
                                    223 ; internal ram data
                                    224 ;--------------------------------------------------------
                                    225 	.area DSEG    (DATA)
                                    226 ;--------------------------------------------------------
                                    227 ; overlayable items in internal ram 
                                    228 ;--------------------------------------------------------
                                    229 	.area	OSEG    (OVR,DATA)
      000008                        230 _send_PARM_2:
      000008                        231 	.ds 1
                                    232 ;--------------------------------------------------------
                                    233 ; Stack segment in internal ram 
                                    234 ;--------------------------------------------------------
                                    235 	.area	SSEG
      000009                        236 __start__stack:
      000009                        237 	.ds	1
                                    238 
                                    239 ;--------------------------------------------------------
                                    240 ; indirectly addressable internal ram data
                                    241 ;--------------------------------------------------------
                                    242 	.area ISEG    (DATA)
                                    243 ;--------------------------------------------------------
                                    244 ; absolute internal ram data
                                    245 ;--------------------------------------------------------
                                    246 	.area IABS    (ABS,DATA)
                                    247 	.area IABS    (ABS,DATA)
                                    248 ;--------------------------------------------------------
                                    249 ; bit data
                                    250 ;--------------------------------------------------------
                                    251 	.area BSEG    (BIT)
                                    252 ;--------------------------------------------------------
                                    253 ; paged external ram data
                                    254 ;--------------------------------------------------------
                                    255 	.area PSEG    (PAG,XDATA)
                                    256 ;--------------------------------------------------------
                                    257 ; external ram data
                                    258 ;--------------------------------------------------------
                                    259 	.area XSEG    (XDATA)
                                    260 ;--------------------------------------------------------
                                    261 ; absolute external ram data
                                    262 ;--------------------------------------------------------
                                    263 	.area XABS    (ABS,XDATA)
                                    264 ;--------------------------------------------------------
                                    265 ; external initialized ram data
                                    266 ;--------------------------------------------------------
                                    267 	.area XISEG   (XDATA)
                                    268 	.area HOME    (CODE)
                                    269 	.area GSINIT0 (CODE)
                                    270 	.area GSINIT1 (CODE)
                                    271 	.area GSINIT2 (CODE)
                                    272 	.area GSINIT3 (CODE)
                                    273 	.area GSINIT4 (CODE)
                                    274 	.area GSINIT5 (CODE)
                                    275 	.area GSINIT  (CODE)
                                    276 	.area GSFINAL (CODE)
                                    277 	.area CSEG    (CODE)
                                    278 ;--------------------------------------------------------
                                    279 ; interrupt vector 
                                    280 ;--------------------------------------------------------
                                    281 	.area HOME    (CODE)
      000000                        282 __interrupt_vect:
      000000 02 00 06         [24]  283 	ljmp	__sdcc_gsinit_startup
                                    284 ;--------------------------------------------------------
                                    285 ; global & static initialisations
                                    286 ;--------------------------------------------------------
                                    287 	.area HOME    (CODE)
                                    288 	.area GSINIT  (CODE)
                                    289 	.area GSFINAL (CODE)
                                    290 	.area GSINIT  (CODE)
                                    291 	.globl __sdcc_gsinit_startup
                                    292 	.globl __sdcc_program_startup
                                    293 	.globl __start__stack
                                    294 	.globl __mcs51_genXINIT
                                    295 	.globl __mcs51_genXRAMCLEAR
                                    296 	.globl __mcs51_genRAMCLEAR
                                    297 	.area GSFINAL (CODE)
      00005F 02 00 03         [24]  298 	ljmp	__sdcc_program_startup
                                    299 ;--------------------------------------------------------
                                    300 ; Home
                                    301 ;--------------------------------------------------------
                                    302 	.area HOME    (CODE)
                                    303 	.area HOME    (CODE)
      000003                        304 __sdcc_program_startup:
      000003 02 00 6D         [24]  305 	ljmp	_main
                                    306 ;	return from main will return to caller
                                    307 ;--------------------------------------------------------
                                    308 ; code
                                    309 ;--------------------------------------------------------
                                    310 	.area CSEG    (CODE)
                                    311 ;------------------------------------------------------------
                                    312 ;Allocation info for local variables in function 'send'
                                    313 ;------------------------------------------------------------
                                    314 ;c                         Allocated with name '_send_PARM_2'
                                    315 ;d                         Allocated to registers 
                                    316 ;------------------------------------------------------------
                                    317 ;	sort.c:3: void send (char d,char c) {
                                    318 ;	-----------------------------------------
                                    319 ;	 function send
                                    320 ;	-----------------------------------------
      000062                        321 _send:
                           000007   322 	ar7 = 0x07
                           000006   323 	ar6 = 0x06
                           000005   324 	ar5 = 0x05
                           000004   325 	ar4 = 0x04
                           000003   326 	ar3 = 0x03
                           000002   327 	ar2 = 0x02
                           000001   328 	ar1 = 0x01
                           000000   329 	ar0 = 0x00
      000062 85 82 80         [24]  330 	mov	_P0,dpl
                                    331 ;	sort.c:5: P1 = c;
      000065 85 08 90         [24]  332 	mov	_P1,_send_PARM_2
                                    333 ;	sort.c:6: }
      000068 22               [24]  334 	ret
                                    335 ;------------------------------------------------------------
                                    336 ;Allocation info for local variables in function 'terminate'
                                    337 ;------------------------------------------------------------
                                    338 ;	sort.c:8: void terminate() {P3 = 0x55;}
                                    339 ;	-----------------------------------------
                                    340 ;	 function terminate
                                    341 ;	-----------------------------------------
      000069                        342 _terminate:
      000069 75 B0 55         [24]  343 	mov	_P3,#0x55
      00006C 22               [24]  344 	ret
                                    345 ;------------------------------------------------------------
                                    346 ;Allocation info for local variables in function 'main'
                                    347 ;------------------------------------------------------------
                                    348 ;	sort.c:10: void main()
                                    349 ;	-----------------------------------------
                                    350 ;	 function main
                                    351 ;	-----------------------------------------
      00006D                        352 _main:
                                    353 ;	sort.c:12: send (4,2); // 1
      00006D 75 08 02         [24]  354 	mov	_send_PARM_2,#0x02
      000070 75 82 04         [24]  355 	mov	dpl,#0x04
      000073 12 00 62         [24]  356 	lcall	_send
                                    357 ;	sort.c:13: send (7,9); // 2
      000076 75 08 09         [24]  358 	mov	_send_PARM_2,#0x09
      000079 75 82 07         [24]  359 	mov	dpl,#0x07
      00007C 12 00 62         [24]  360 	lcall	_send
                                    361 ;	sort.c:14: send (8,1); // 3
      00007F 75 08 01         [24]  362 	mov	_send_PARM_2,#0x01
      000082 75 82 08         [24]  363 	mov	dpl,#0x08
      000085 12 00 62         [24]  364 	lcall	_send
                                    365 ;	sort.c:15: send (9,3); // 4
      000088 75 08 03         [24]  366 	mov	_send_PARM_2,#0x03
      00008B 75 82 09         [24]  367 	mov	dpl,#0x09
      00008E 12 00 62         [24]  368 	lcall	_send
                                    369 ;	sort.c:16: send (2,6); // 5
      000091 75 08 06         [24]  370 	mov	_send_PARM_2,#0x06
      000094 75 82 02         [24]  371 	mov	dpl,#0x02
      000097 12 00 62         [24]  372 	lcall	_send
                                    373 ;	sort.c:17: send (1,8); // 6
      00009A 75 08 08         [24]  374 	mov	_send_PARM_2,#0x08
      00009D 75 82 01         [24]  375 	mov	dpl,#0x01
      0000A0 12 00 62         [24]  376 	lcall	_send
                                    377 ;	sort.c:18: send (5,9); // 7
      0000A3 75 08 09         [24]  378 	mov	_send_PARM_2,#0x09
      0000A6 75 82 05         [24]  379 	mov	dpl,#0x05
      0000A9 12 00 62         [24]  380 	lcall	_send
                                    381 ;	sort.c:19: send (4,4); // 8
      0000AC 75 08 04         [24]  382 	mov	_send_PARM_2,#0x04
      0000AF 75 82 04         [24]  383 	mov	dpl,#0x04
      0000B2 12 00 62         [24]  384 	lcall	_send
                                    385 ;	sort.c:21: terminate();
                                    386 ;	sort.c:22: }
      0000B5 02 00 69         [24]  387 	ljmp	_terminate
                                    388 	.area CSEG    (CODE)
                                    389 	.area CONST   (CODE)
                                    390 	.area XINIT   (CODE)
                                    391 	.area CABS    (ABS,CODE)
