# pystatdump
CUBRID statistics visualizer in Python

pystatdump.py -i <inputfile> ; statdump file output by CUBRID statdump utility (for better display in graphs rename it with version name)
              -m <mode> | --mode=<mode>; possible values corr1, corr2, stack
              --sar-file=<SAR file path>
              --iostat-file=<IOSTAT file path>
              --graph-mode=<output of graphs>
              --corr1-key=<string>
              -p; --prefix=<string>
              --corr1-th=<correlation_threshold 1> -corr2-th=<correlation_threshold 2>
              --stats-filter-file=<file containing desired stats (by default all stats are read)

  mode : corr1 : finds best correlations amount other keys for key provided by corr1-key argument
  mode : corr2 : for two instance of test (provided using prefix argument ), provides key which do not match (exceeds the correlation threshold)
  mode : stack : build stacked graphs (output in files) of each statistic from several versions (each specified by --prefix)
  corr1-key : name of statistic to be used for finding best correlation within range 
  corr1-th : first value of threshold (for corr1 mode is mininum the first column)
  corr2-th : second value of threshold (for corr1 mode is maximum of second column)
  graph-mode : 0 : display; 1 : file : 2 : both file and display

  Multiple -i -iostat-file -sar-file -prefix arguments may be provided, composing a list of arguments of the same kind.
  The order of --prefix argument matters in stack mode for the order of drawing
