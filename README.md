## download miniseq data and demultiplex
wget "https://api.bintray.com/content/basespace/BaseSpaceCLI-EarlyAccess-BIN/latest/\$latest/amd64-linux/bs?bt_package=latest" -O $HOME/bin/bs
chmod u+x bs
./bs auth
# If your samples were successfully demultiplexed:
### conda activate basespace
### ~/bin/bs list projects
### ~/bin/bs download project -i #####2898 -o ~/projectname/raw
### ~/bin/bs download project -i ####82897 -o . --extension=fastq.gz
# To demultiplex locally (not on BaseSpace):
#### ~/bin/bs list runs
#### ~/bin/bs download run -i 17903NNNN -o fatimaseq2
#### 
#### bcl2fastq -R path/to/bcl_dir --sample-sheet Import_BiologicalSamples_fatimaseq2.csv -o fastqs
#### 
##### PhiX is not indexed, so we need to map the undetermined reads to PhiX to get the percent phiX
#### bwa mem phiX.fa R1.fq R2.fq > phix.sam


#### primer key:
#### Mt_cox1_F	TTGGGTCTCCTCCTCCAA
#### Mt_cox1_R	GGAGCTCCTGATATAGCTTTCC
#### Mt_cox1_short_F	TCGATCAAGAGTAATACCTGAAGAT
#### Mt_cox1_short_R	AGCTGGAACTGGATGAACAG
#### Or62_F	ATCGCAGTCTCCAGAAAGGACC
#### Or62_R	TGCATTTGTAGCGATCAGCCCC
#### kdr_TT_F	GGCCACCGTAGTGATAGGAAAC
#### kdr_TT_R	TACAGACTCCTACCTCCGGA
#### cytb_mini_F	CCATCCAACATCTCAGCATGATGAAA
#### cytb_mini_R	CCCCTCGAATGATATTTGTCCTCA
#### 16S_F	CCTACGGGNGGCWGCAG
#### 16S_R	GACTACHVGGGTATCTAATCC
#### plant_F_cA49325	CGAAATCGGTAGACGCTACG
#### plant_R_dB49863	GGGGATAGAGGGACTTGAAC
#### rbcL_F_new	CTTACCAGYCTTGATCGTTACAAAGG
#### rbcL_R	GTAAAATCAAGTCCACCRCG
#### >panFil_F	TGATTGGTGGTTTTGGTAA
#### >panFil_R	ATAAGTACGAGTATCAATATC
#### Ctar_472_F	GTTCTAGCAATGACAGTGTTGGT
#### Ctar_472_R	GTTCGTACGCTGCAGGACTT
#### ace1_F	CCGTCATGCTGTGGATCTT
#### ace1_R	AAACCACGATCACGTTCTCC
#### Ctar_236_F	AACCTCTGGTGCACGATCC
#### Ctar_236_R	ACGTGGCTCTCGAACTGC
#### NextRAD_GTG	GTGTAGAGC
#### NextRAD_472	CAGTGTTGGT

#### see Weir 2003 for ace-1 mutation G119S:
https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-2583.2004.00452.x?sid=nlm%3Apubmed
