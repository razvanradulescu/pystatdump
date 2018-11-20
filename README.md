# pystatdump
CUBRID statistics visualizer in Python

The tool is able to load multiple CUBRID statdump output file, SAR output files, IOSTAT output files.
If at least two files of the same type are provided, all statistics are prefixed by filename of origin, otherwise no prefix is set to simplify operation.

All samples are gathered into one data container and mixed (using samples from SAR, IOSTAT, STATDUMP) analysis may be performed.

There are three modes of operation:
 - stack : draws graphs for multiple version of the same statistics on the same picture; an image contains only one statistics.
 - corr1 : by providing a reference statistics (prefix.name), a comparison is performed on all other samples and if a correlation exceeding a threshold is found, a corresponding message is displayed and the comparative graph is shown.
        Usage hint: investigating the reasons for behavior of a statistic
 - corr2 : by providing two test instances (with the --prefix argument), by comparing the samples of the same name (suffix), if a strong correlation is not found, a correspoding message is displayed and the comparative graph is shown.
        Usage hint: find which values are "more different" between two runs.
