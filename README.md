Read Until with *npGraph*
========================
This is a fork repo from the original Read Until code with some modifications to adapt our assembly pipeline using
*npGraph*

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
$ ru_assembly
usage:  Read Until API: ru_assembly (/home/sonhoanghguyen/sw/ont/read_until/lib/python3.5/site-packages/ru/ru_npgraph.py)
        [-h] [--host HOST] [--port PORT] --device DEVICE --experiment-name
        EXPERIMENT-NAME [--read-cache READ_CACHE] [--workers WORKERS]
        [--channels CHANNELS CHANNELS] [--run-time RUN-TIME]
        [--unblock-duration UNBLOCK-DURATION] [--cache-size CACHE-SIZE]
        [--batch-size BATCH-SIZE] [--throttle THROTTLE] [--dry-run]
        [--log-level LOG-LEVEL] [--log-format LOG-FORMAT] [--log-file LOG-FILE]
        --toml TOML [--paf-log PAF_LOG] [--chunk-log CHUNK_LOG]
        Read Until API: ru_assembly (/home/sonhoanghguyen/sw/ont/read_until/lib/python3.5/site-packages/ru/ru_npgraph.py): error: the following arguments are required: --device, --experiment-name, --toml

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


