# (Yet another) ESP32 backtrace decoder

A Python3-based utility to decode ESP32(S3) backtraces.

There are a couple of ESP32 stacktrace or backtrace decoders out there, but it
seems none of them are compatible with this format:

```
abort() was called at PC 0x401b1d17 on core 1
Backtrace: 0x40083c8d:0x3ffd8490 0x4008f1dd:0x3ffd84b0 [...]
ELF file SHA256: f28c897288706a53
```

Those are lines produced by OpenDTU firmware on an ESP32(S3) chip. The firmware
is built by Platformio, and when Platformio monitor is active, it will
auto-translate the backtrace to lines of code. Creating this tool seemed less
tedious than finding the monitor plugin/filter implementation and figuring out
how to use it stand-alone.

## Requirements

* Python 3
* Probably only works on Linux
* Platformio installation that was used at least once to build for the platform
  in question, such that the respective host tools are available.
