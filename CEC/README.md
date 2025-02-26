# CEC Competitions on Real-Parameter Single Objective Optimization

## Requirements

- [Python](https://www.python.org/downloads/) >= 3.6
- [Cython](https://cython.org/)
- [NiaPy](https://github.com/NiaOrg/NiaPy)

## Installation

1. Install [NiaPy](https://github.com/NiaOrg/NiaPy).
2. Clone or download [NiaPy-examples](https://github.com/NiaOrg/NiaPy-examples).
3. Navigate to one of the CEC competitions folders, e.g. to `cec2018` by running `cd cec2018`.
4. Build the library by running `make build`.
5. Shared library should be installed.
6. For a simple run, navigate `cd ..` and run `python run_cec.py -a BatAlgorithm -c 18 -r log`.
7. If build has been successful, simple run should output function values and coordinates.

## Program parameters

Following command line program parameters are applicable for [NiaPy-examples](https://github.com/NiaOrg/NiaPy-examples):
- `-a` or `--algorithm`: Name of algorithm to use (name of the class of the algorithm in NiaPy).
- `-n` or  `--population-size`: Number of individuals in population.
- `--seed`: Set the starting seed of algorithm run. If multiple runs, user can provide list of ints, where each int usd use at new run. Default values is `None`.
- `-c` or `--cec`: Set the year of CEC competition, options: `8, 13, 14, 15, 17, 18, 19, 21`, e.g. `-c 18`.
- `-f` or `--fnum`: Set the function number, options: unsigned integers, vary by the benchmark used, e.g. `-f 12`.
- `-sr` or `--srange`: Set the lower and upper limit of search space for selected function, options: positive and negative real numbers (first number lower than the second).
- `-d` or `--dimension`: Set the number of dimensions, options: `10, 30, 50, 100`, e.g. `-d 10`.
- `-nr` or `--nFESreduc`: Set the number of evaluations reduction factor, options: `0.01, 0.02, 0.03, 0.05, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0`.
- `-r` or `--run-type`: Run type of run. If not provided, multiple runs of the algorithm are executed, and the best position and fitness of each run get logged. Value can be:
  - `log`: Single run. Output is shown every time new global best solution is found
  - `plot`: Single run. Convergence graph is generated and shown.
- `-rn` or `--rnum`: Set the number of runs per selected function, only applicable when run type is not provided. Options: positive integers.
- `-o` or `--wout`: If this flag is set, and no run type is provided, the results of the algorithm runs will be saved to 2 files in the current working directory:
  - `<algorithm_acronym>_<fnum>_<dimension>_p` - containing the best positions of each run.
  - `<algorithm_acronym>_<fnum>_<dimension>_v` - containing the best fitness values of each run.

## Run example

Run command: `python run_cec.py -a 'AnarchicSocietyOptimization' -d 10 -f 12 -r log -c 18`

Output of run command:
```
INFO:niapy.task.Task:evals:1 => 15887977932.650658
INFO:niapy.task.Task:evals:2 => 2882836746.7784734
INFO:niapy.task.Task:evals:305 => 2827714408.420182
INFO:niapy.task.Task:evals:516 => 458871069.1209142
INFO:niapy.task.Task:evals:1031 => 413517756.67584217
INFO:niapy.task.Task:evals:1143 => 263646886.2918284
INFO:niapy.task.Task:evals:1271 => 263646695.0180283
INFO:niapy.task.Task:evals:1529 => 257682254.06217128
INFO:niapy.task.Task:evals:1658 => 257682145.16393614
INFO:niapy.task.Task:evals:2174 => 257682121.14064276
INFO:niapy.task.Task:evals:2520 => 45392790.34755093
INFO:niapy.task.Task:evals:2777 => 45392787.31286106
INFO:niapy.task.Task:evals:3422 => 45392785.75051703
INFO:niapy.task.Task:evals:3705 => 42569266.46314
INFO:niapy.task.Task:evals:3810 => 33647333.52087131
INFO:niapy.task.Task:evals:3938 => 31135887.920171045
INFO:niapy.task.Task:evals:4325 => 28006861.40584898
INFO:niapy.task.Task:evals:4327 => 28006858.803725045
INFO:niapy.task.Task:evals:4404 => 25383134.883275196
INFO:niapy.task.Task:evals:4790 => 23960011.731594462
INFO:niapy.task.Task:evals:4919 => 17041796.939870246
INFO:niapy.task.Task:evals:5048 => 17041681.15559607
INFO:niapy.task.Task:evals:5381 => 13242688.98038855
INFO:niapy.task.Task:evals:6542 => 10979445.399338886
INFO:niapy.task.Task:evals:6671 => 9569962.773170047
INFO:niapy.task.Task:evals:7241 => 8843648.722731521
INFO:niapy.task.Task:evals:7499 => 7878356.475888453
INFO:niapy.task.Task:evals:7975 => 5660639.594883495
INFO:niapy.task.Task:evals:8747 => 4720735.314137558
INFO:niapy.task.Task:evals:8832 => 4229079.267252325
INFO:niapy.task.Task:evals:9863 => 4192362.417151575
INFO:niapy.task.Task:evals:10766 => 3928393.071632758
INFO:niapy.task.Task:evals:13422 => 3562200.322962117
INFO:niapy.task.Task:evals:13606 => 3231413.1068499987
INFO:niapy.task.Task:evals:14378 => 3231389.431187782
INFO:niapy.task.Task:evals:14638 => 3231327.5379638397
INFO:niapy.task.Task:evals:14897 => 2732412.312267562
INFO:niapy.task.Task:evals:17081 => 2552131.6789135947
INFO:niapy.task.Task:evals:17608 => 1605007.9284521122
INFO:niapy.task.Task:evals:20083 => 1559596.0823314413
INFO:niapy.task.Task:evals:20210 => 1359770.5835466697
INFO:niapy.task.Task:evals:20833 => 1235758.4475912028
INFO:niapy.task.Task:evals:21605 => 1118855.4237355953
INFO:niapy.task.Task:evals:22274 => 1034285.4301890817
INFO:niapy.task.Task:evals:22897 => 950911.0876368887
INFO:niapy.task.Task:evals:23542 => 950898.5680112189
INFO:niapy.task.Task:evals:24314 => 652860.5444559973
INFO:niapy.task.Task:evals:24831 => 646343.5793750585
INFO:niapy.task.Task:evals:28329 => 278317.8140921296
INFO:niapy.task.Task:evals:29489 => 160343.96685996052
INFO:niapy.task.Task:evals:41230 => 160329.04618740454
INFO:niapy.task.Task:evals:45229 => 160319.03922335315
INFO:niapy.task.Task:evals:45361 => 160304.23257632973
INFO:niapy.task.Task:evals:48584 => 160303.56354332485
INFO:niapy.task.Task:evals:49099 => 160303.36117476295
INFO:niapy.task.Task:evals:49226 => 160300.92693932337
INFO:niapy.task.Task:evals:49312 => 141667.7820242949
INFO:niapy.task.Task:evals:59502 => 141647.80897604302
INFO:niapy.task.Task:evals:62728 => 137161.7192115172
INFO:niapy.task.Task:evals:64534 => 137116.6433675834
INFO:niapy.task.Task:evals:66467 => 137109.53848547916
INFO:niapy.task.Task:evals:72425 => 119679.76450540649
INFO:niapy.task.Task:evals:73306 => 106813.72813861225
INFO:niapy.task.Task:evals:78337 => 106810.48554636036
INFO:niapy.task.Task:evals:79544 => 97633.54249492753
INFO:niapy.task.Task:evals:81328 => 83056.24696309568
INFO:niapy.task.Task:evals:85067 => 65795.97363641771
INFO:niapy.task.Task:evals:85585 => 65758.66064004379
INFO:niapy.task.Task:evals:86616 => 46172.777363265704
INFO:niapy.task.Task:evals:92275 => 42730.68650210336
INFO:niapy.task.Task:evals:92402 => 42561.52670833116
INFO:niapy.task.Task:evals:96530 => 42515.45691543244
INFO:niapy.task.Task:evals:99626 => 42493.07447795165
INFO:cec_run:[85.84445158791526 22.23219904175823 -97.32944594919638 79.9887304959317 -18.152119984642393 24.58947952179201 -37.21712401925737 22.715163652913745 -4.25470310702339 31.790839431648358] 42493.07447795165
```
