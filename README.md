# HollowFind
Hollowfind is a Volatility plugin to detect different types of process hollowing techniques used in the wild to bypass, confuse, deflect and divert the forensic analysis techniques. The plugin detects such attacks by finding discrepancy in the VAD and PEB, it also disassembles the address of entry point to detect any redirection attempts and also reports any suspicious memory regions which should help in detecting any injected code.

Full details can be found in the link:
https://cysinfo.com/detecting-deceptive-hollowing-techniques/

### Running the Plugin

Copy the plugin to volatility/plugins directory

Run the plugin against memory image as shown below

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 hollowfind
```

### Other Options

To filter on a specic process id use -p option

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 hollowfind -p 1820
```

To filter on multiple process ids use -p followed by comma seperated process ids

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 hollowfind -p 1820,868
```

To dump the suspicious memory regions use -D followed by directory name

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 hollowfind -p 1820 -D dump/
```

To redirect the output to file use --output-file option

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 hollowfind --output-file=output.txt
```




