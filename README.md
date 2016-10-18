Synthesizable lossless compression decoders
===========================================

Introduction
------------
This software package contains source code of synthesizable C/C++ code version of lossless compression decoders.

The source code is largely modified and rewritten based on the Reference Software codes, i.e. High-level Synthesis tools are able to synthesize the source code to RTL. The decoders accept modified compressed data as input and raw data as output. This software package also provides the TCL script which automatically run the HLS and RTL cosimulation process for the RTL lossless compression decoders.



Reference Software codes
----------------
1.Run length encoding/decoding reference software. (2013) Available: https://sourceforge.net/projects/nikkhokkho/files/RLE64/

2.LZ77 reference software. (2004) Available: https://sourceforge.net /projects/compressions/

3.LZSS reference software. Available: https://oku.edu.mie-u.ac.jp/~okumura/compression/lzss.c

4.liblzg reference software. (2014) Available: http://liblzg.bitsnbites.eu/



Test Case Source
----------------
1. Full Bitstreams. 
	ReCoNets. [Online] Available: http://www.reconets.de/bitstreamcompression/
2. Partial Bitstreams.
	Thirty three partial bitstreams are developed by Vivado 2015.4.
3. Software Binaries.
	A. Sarangi, S. MacMahon, and U. Cherukupaly, “LightWeight IP Application Examples,” Xilinx Appplication Note, XAPP1026 (v5.1), Xilinx Inc., San Jose, CA, Nov. 2014.

We use the above four reference software codes to compress/decompress the full bitstreams, partial bitstreams, and software binaries.
If you want to use the four reference software codes to compress the benchmark files. Please compile first as instructed on the corresponding website. 
Then modify the compressed files for hardware evaluation.
The modified compressed files and raw files are provided.
Example
---------------------------------------------------------------------------------------------
	./benchmark/Bitstream/RLE_32bit/compress_1 
			output of the rle software encoder.
	./benchmark/Bitstream/RLE_32bit/compress_1_hw 
			modify the output of the rle software encoder for hardware evaluation..
----------------------------------------------------------------------------------------------------------



HLS tool requirement
--------------------
This code is tested under Xilinx Vivado High-level Synthesis (HLS) tool version 2015.4.  
Please make sure Vivado HLS is installed and make sure command line `vivado_hls` takes effect by updating your environment variable PATH.



Usage
-------------------------------------------------------------
1. Open the Vivado HLS Command Prompt.
	->>On Windows, use Start > All Programs > Xilinx Design Tools > Vivado 2015.4 >Vivado HLS > Vivado HLS 2015.4 Command Prompt.
	->>On Linux, open a new shell.

2. Change directory to the corresponding directory

3. In the Vivado HLS Command Prompt window, type
	->>vivado_hls -f script.tcl

	Vivado HLS executes all the steps: C verification, Synthesis, and cosimulation (using Verilog with xsim as simulator). When finished, the results are available inside the project directory.

  The simulation results are available in /solution/sim/report.

  The synthesis report is available in ./solution1/syn/report.

  The co-simulation results are available in /solution/csim/report.

  The output package is available in /solution1/impl/ip.

  The final output RTL is available in /solution1/impl and then Verilog or VHDL.



Contact
-------
For bug report, please contact Jian Yan (Jian_Yan_CN_at_hotmail.com).


