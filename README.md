# This is a fork repo from ReadUntil with customization to work with *npGraph*

Read Until
==========

If you are anything like us, reading a README is the last thing you do when running code. 
PLEASE DON'T DO THAT FOR READ UNTIL. This will effect changes to your sequencing and - 
if you use it incorrectly - cost you money. We have added a [list of GOTCHAs](#common-gotchas) 
at the end of this README. We have almost certainly missed some... so - if something goes 
wrong, let us know so we can add you to the GOTCHA hall of fame!

This is a Python3 package that integrates with the 
[Read Until API](https://github.com/nanoporetech/read_until_api). However, we use 
a slightly modified version - [Read Until API V2](https://github.com/looselab/read_until_api_v2).  

The Read Until API provides a mechanism for an application to connect to a
MinKNOW server to obtain read data in real-time. The data can be analysed in the
way most fit for purpose, and a return call can be made to the server to unblock
the read in progress and so direct sequencing capacity towards reads of interest.

**This implementation of Read Until requires Guppy version 3.4 or newer. It will 
not work on earlier versions.**

**Currently we only recommend LINUX for running Read Until. We have not had 
effective performance on other platforms to date.**

The code here has been tested with Guppy in GPU mode using GridION Mk1 and 
NVIDIA RTX2080 on live sequencing runs and an NIVIDA GTX1080 using playback 
on a simulated run (see below for how to test this).  
This code is run at your own risk as it DOES affect sequencing output. You 
are **strongly** advised to test your setup prior to running (see below for 
example tests).

Citation
--------
If you use this software please cite: [10.1101/2020.02.03.926956](https://dx.doi.org/10.1101/2020.02.03.926956)

> Payne A, Holmes N, Clarke T, Munro R, Debebe B and Loose M (2020) Nanopore adaptive sequencing for mixed samples, 
>whole exome capture and targeted panels. Cold Spring Harbor Laboratory.

Installation
------------
```bash
# Make a virtual environment
python3 -m venv read_until
. ./read_until/bin/activate
pip install --upgrade pip

# Install our Read Until API
pip install git+https://github.com/LooseLab/read_until_api_v2@master
pip install git+https://github.com/hsnguyen/ru@master
```

Usage
-----
```bash
# check install
$ ru_generators
usage: Read Until API: ru_assembly (ru_npgraph.py)
       [-h] [--host HOST] [--port PORT] --device DEVICE --experiment-name
       EXPERIMENT-NAME [--read-cache READ_CACHE] [--workers WORKERS]
       [--channels CHANNELS CHANNELS] [--run-time RUN-TIME]
       [--unblock-duration UNBLOCK-DURATION] [--cache-size CACHE-SIZE]
       [--batch-size BATCH-SIZE] [--throttle THROTTLE] [--dry-run]
       [--log-level LOG-LEVEL] [--log-format LOG-FORMAT] [--log-file LOG-FILE]
       --toml TOML [--paf-log PAF_LOG] [--chunk-log CHUNK_LOG]

# example run command - change arguments as necessary:
$ ru_assembly --experiment-name "Test run" --device MN17073 --toml example.toml --log-file RU_log.log
```

TOML File
---------
For information on the TOML files see [TOML.md](TOML.md).

Testing
-------
To test Read Until using *npGraph* on your configuration we recommend first running a playback 
experiment to test unblock speed and then selection.

blah blah


