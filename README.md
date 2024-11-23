# 🐧 tuxedo-drivers-kmod 

> ⚠️ WARNING: WIP!! Some features are missing!

RPM spec files to build the [tuxedo-drivers](https://gitlab.com/tuxedocomputers/development/packages/tuxedo-drivers) as kmod. 

# 📚 Table of Contents 

- [🧩 Included modules](#included-modules)
- [🛠️ Build](#build)
- [📦 Install](#install)
- [✅ Check if the modules are loaded](#check)
- [🗺️ Roadmap](#roadmap)

## 🧩 Included modules <a id="included-modules"></a>

- tuxedo_compatibility_check
- tuxedo_keyboard
- clevo_acpi
- clevo_wmi
- uniwill_wmi
- tuxedo_io
- tuxedo_nb02_nvidia_power_ctrl
- ite_8291
- ite_8291_lb
- ite_8297
- ite_829x
- tuxedo_nb05_ec
- tuxedo_nb05_power_profiles
- tuxedo_nb05_sensors
- tuxedo_nb05_keyboard
- tuxedo_nb05_kbd_backlight
- tuxedo_nb05_fan_control
- tuxedo_nb04_keyboard
- tuxedo_nb04_wmi_ab
- tuxedo_nb04_wmi_bs
- tuxedo_nb04_sensors
- tuxedo_nb04_power_profiles
- tuxedo_nb04_kbd_backlight
- stk8321
- gxtp7380
- tuxedo_tuxi_fan_control
- tuxi_acpi

## 🛠️ Build <a id="build"></a>

### rpmbuild

You can build it for your kernel with:
```sh
./build.sh
```

## 📦 Install <a id="install"></a>

After build you can install the rpm for your kernel:
```sh
dnf install ~/rpmbuild/RPMS/x86_64/tuxedo-drivers-kmod-common-4.11.2-1.fc41.x86_64.rpm ~/rpmbuild/RPMS/x86_64/kmod-tuxedo-drivers-$(uname -r).x86_64-4.11.2-1.fc41.x86_64.rpm
```

## ✅ Check if the modules are loaded <a id="check"></a>

Check if all modules are loaded:

```sh
lsmod | grep tux
```

Else you can load it with:

```sh
./modprobe.sh
```

Some modules could fail if they are not supported with your hardware.

## 🗺️ Roadmap <a id="roadmap"></a>

- [x] Port tuxedo-drivers to akmod
- [ ] Testing the modules
- [ ] Test with [tuxedo-control-center](https://github.com/tuxedocomputers/tuxedo-control-center)
- [ ] Test with [tuxedo-rs](https://github.com/AaronErhardt/tuxedo-rs)
- [ ] Publish to copr
- [ ] Integrate into [akmods](https://github.com/ublue-os/akmods)
- [ ] Test on different devices
- [ ] Integrate into [bluefin](https://github.com/ublue-os/bluefin)
