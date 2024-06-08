# headset-utils

Library for communicating with various AR headsets and abstracting common utilities that can be used by other applications.

* Rokid Air, Max
* XREAL Air, Air 2, and Air 2 Pro, Light
* MGrawoow G530 (a.k.a. Metavision M53)
* Mad Gaze Glow

### Build and run

Install dependencies rust and libudev.

```
sudo apt install cargo libudev-dev libstdc++-12-dev
cargo update
```

Add the udev scripts to your udev config, so the glasses are available without sudo:

```
sudo cp udev/* /etc/udev/rules.d/
sudo udevadm control --reload-rules && sudo udevadm trigger
```

Build and ensure that euler angles are printing to console:

```
cargo build --release --example euler_60
target/release/examples/euler_60
```