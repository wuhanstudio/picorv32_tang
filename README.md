# Picorv32 + RT-Thread on Lichee Tange (EG4S20)

## Step 1 - Build rt-thread firmware

```
$ cd rtthread-nano/rt-thread/bsp/picorv32_blink/
$ mkdir build
$ cd build
$ cmake ../
$ make
$ cd ../../../../../
```

## Step 2 - Generate Memory Initialization File (MIF) from rt-thread.bin

Build firmware:

```
$ cp rtthread-nano/rt-thread/bsp/picorv32_blink/build/rt-thread.bin bin2mif/
$ cd bin2mif
$ python3 bin2mif.py rt-thread.bin rt-thread.mif
$ cd ../
```
Copy generated rt-thread.mif to FPGA project directory:

```
$ cp bin2mif/rt-thread.mif picorv32_EG4S20/firmware/
```
## Step 3 - Upload bitsream
