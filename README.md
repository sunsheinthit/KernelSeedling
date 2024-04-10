# A Kernel Seedling

In this lab, I worked with a virtual machine to create a kernel module that returns the number of running processes. Then, I inserted this module into the kernel, and ran it.

I put sudo insmod proc_count.ko under both building and running becasue it
inserts the module into the kernel, and initiating the module's operation.

## Building

```shell
make
```

## Running

```shell
sudo insmod proc_count.ko
cat /proc/count
```

The first command initiates the module for us, and was programmed to output the results into the "count" file. The second command lets us see the contents of the count file, which is the number of running processes.

## Cleaning Up

```shell
make clean
sudo rmmod proc_count
```

make clean will remove all of the binary files created
sudo rmmod proc_count will remove proc_count from the module

## Testing

```python
python -m unittest
```

results:
...
Ran 3 tests in 13.556s

OK

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```

kernel ver:
Linux 5.14.8-arch1-1 #1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000
