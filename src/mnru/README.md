       =============================================================
       COPYRIGHT NOTE: This source code, and all of its derivations,
       is subject to the "ITU-T General Public License". Please have
       it  read  in    the  distribution  disk,   or  in  the  ITU-T
       Recommendation G.191 on "SOFTWARE TOOLS FOR SPEECH AND  AUDIO
       CODING STANDARDS".
       =============================================================

This text describes the necessary files for the UGST MNRU module:

Source files:
===
mnru.h:		prototypes and definitions for MNRU routines
		and data structures. Depends on MNRU.C.
mnru.c:		Functions for MNRU operation; this is the
		module itself. Depends on MNRU.H.

Demo and support files:
===
mnrudemo.c:	This is ONLY a demontration program for the MNRU
		module. Depends on UGSTDEMO.H, MNRU.H and MNRU.C.
ugstdemo.h:	Prototypes and definitions for UGST demo programs (in ../utl).
calc-snr.c:     SNR calculation function
snr.c:          Driving program for SNR calculation
ugst-utl.c:     Contains conversion routines (found in directory utl)

Makefiles:
===
Makefiles have been provided for automatic build-up of the executable program
and to process the test files:
make-vms.com: ... DCL for VAX/VMS Vax-cc compiler or the VMS port of gcc
makefile.cl: .... makefile for MS Visual C Compiler
makefile.tcc: ... makefile for MSDOS Borland tcc
makefile.djc: ... makefile for MSDOS port of gcc
makefile.unx: ... makefile for Unix, using either cc (Sun), acc (Sun), or gcc

Testing:
===
The provided makefiles can run a portability test on the demo program. They
need the archive sine-ref.zip ([pk]zip compatible archive) and [pk]unzip to
extract the proper source and reference processed files. The contents of this
archive file is, as reported by unzip:

 Length  Method   Size  Ratio   Date    Time   CRC-32     Name
 ------  ------   ----  -----   ----    ----   ------     ----
  10240  Deflate   9696   5%  07-28-95  15:34  17694ec1   sine-q00.unx
  10240  Deflate   9604   6%  07-28-95  15:34  33e9b26e   sine-q05.unx
  10240  Deflate   9496   7%  07-28-95  15:34  c18f278a   sine-q10.unx
  10240  Deflate   9436   8%  07-28-95  15:34  b3ff0cb9   sine-q15.unx
  10240  Deflate   9362   9%  07-28-95  15:34  93954528   sine-q20.unx
  10240  Deflate   9318   9%  07-28-95  15:34  64282242   sine-q25.unx
  10240  Deflate   9276   9%  07-28-95  15:34  6b3f5149   sine-q30.unx
  10240  Deflate   9203  10%  07-28-95  15:34  64a81a9b   sine-q35.unx
  10240  Deflate   9166  10%  07-28-95  15:34  38e52f25   sine-q40.unx
  10240  Deflate   9101  11%  07-28-95  15:34  c71212bd   sine-q45.unx
  10240  Deflate   9084  11%  07-28-95  15:34  3432a4d3   sine-q50.unx
  10240  Deflate   9056  12%  07-28-95  15:34  e83f5cac   sine-q99.unx
  10240  Deflate   9043  12%  08-23-94  08:59  99604084   sine.src

NOTE! These files are in the big-endian (high-byte first) format. Therefore,
      before using under MSDOS or VAX/VMS, the files need to be
      byte-swapped.  See unsupported program sb in the ../unsup
      directory. The makefiles provided can automatically extract the
      test files and byte-swap them if an awk utility (e.g. gawk) and
      a pkzip-compatible unarchiver are available at the user's instalation.

-- <simao@ctd.comsat.com> --
