# davyos
根据&lt;一个64位操作系统的设计与实现>,来熟悉操作系统的构建和运行逻辑

rust-in-action里面也有如何实现一个非常简单的内核
注意:
windows上,需要修改一下 Cargo.toml
[package]
name = "fledgeos"
version = "0.1.0"
authors = ["Tim McNamara <author@rustinaction.com>"]
edition = "2021"

[dependencies]
bootloader = "0.9.18"  (或者9系列的最高 9.23也可以)
x86_64 = "0.14"


[package.metadata.bootimage]
build-command = ["build"]

run-command = [
  "qemu-system-x86_64", "-drive", "format=raw,file={}"
]

