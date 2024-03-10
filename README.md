# kart_scale

## Parts

Raspberry Pi <- I2c <- ADC <- load cell
- [SparkFun Qwiic or Stemma QT SHIM for Raspberry Pi / SBC](https://www.adafruit.com/product/4463)
- [Adafruit NAU7802 24-Bit ADC - STEMMA QT / Qwiic](https://www.adafruit.com/product/4538)
- [Raspberry Pi Zero W Budget Pack - Includes Pi Zero W](https://www.adafruit.com/product/3410)

Cable
- [STEMMA QT / Qwiic JST SH 4-pin Cable - 100mm Long](https://www.adafruit.com/product/4210)
- [STEMMA QT / Qwiic JST SH 4-Pin Cable - 50mm Long](https://www.adafruit.com/product/4399)

## Libraries

Rust
- [Raspberry Pi Peripheral Access Library](https://github.com/golemparts/rppal)
- [nau7802-rs](https://crates.io/crates/nau7802)

## Examples:

Rust
- [Raspberry Pi Pico scale](https://github.com/werediver/escale/tree/main)

## Cross Compiling for RPi Zero W

Install [cross and docker](https://github.com/cross-rs/cross/blob/main/docs/getting-started.md).
```
cargo install cross --git https://github.com/cross-rs/cross
```

Build/Deploy/Run
```
cross build --target arm-unknown-linux-gnueabihf
scp target/arm-unknown-linux-gnueabihf/debug/kart_scale pi@scale.local:
ssh -t pi@scale.local ./kart_scale
```
