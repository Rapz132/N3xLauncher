<p align="center">
  <img src="packaging/android/res/drawable-nodpi/launcher_icon.png" width="128" height="128" alt="N3xLauncher Icon" />
</p>

# <p align="center">N3xLauncher</p>

A high-performance native Android launcher and engine for **Minecraft: Java Edition 26.3**, written in pure Rust with `wgpu` (Vulkan & OpenGL ES), with a black & white interface.

**Android 9+ (API 28–35) · Vulkan 1.0+ / GLES 3.0 · Full SAF Read & Write · In-App GitHub Updater · Material 3 Launcher · 260 FPS Uncapped · Java Multiplayer**

[Build Guide](docs/android.md) · [Contributing](CONTRIBUTING_ANDROID.md)

> N3xLauncher is a rebrand of [Horizon Android](https://github.com/GoyDevv/Horizon-Android) by GoyDevv, used under the MIT License.

---

## Visual Showcase

| **Joystick and Crosshair** | **D-pad and Touch Aiming** |
| :---: | :---: |
| ![Fox in a forest with joystick controls](docs/media/android/joystick-fox.png) | ![River and forest with D-pad controls](docs/media/android/dpad-river.png) |

| **Snowy Biome** | **Hypixel Arcade · Java Multiplayer** |
| :---: | :---: |
| ![Snowy landscape on Android](docs/media/android/snow-landscape.png) | ![Hypixel Arcade lobby on Android](docs/media/android/hypixel-arcade.png) |

| **Third-Person View** | **Desert Panorama** |
| :---: | :---: |
| ![Steve on Android with third-person camera](docs/media/android/third-person-desert.png) | ![Desert terrain on Android with touch controls](docs/media/android/desert-panorama.png) |

---

## Key Features

### 🎮 Custom Mobile Controls
- **Four Control Styles**: Dynamic Joystick, Fixed D-pad, MCPE Bedrock controls, and Virtual Pointer.
- **On-Screen Layout Editor**: Freely reposition, resize, and adjust the opacity of every touch widget.
- **Quick-Action Menu**: Centered floating menu bubble with instant access to settings, inventory, and perspective toggles.
- **Hardware Input**: Full support for physical keyboards, mice, Bluetooth controllers, and USB gamepads.

### ⚡ Engine & Rendering
- **Vulkan & GLES Backends**: Optimized Vulkan renderer with fallback to OpenGL ES for legacy 32-bit and PowerVR devices.
- **Resolution Scaling**: Scale internal render resolution from 25% to 100% to maximize performance on any chipset.
- **Low-Latency Audio & Haptics**: High-fidelity sound powered by AAudio, with customizable haptic vibration feedback.
- **Cave & Entity Culling**: Aggressive GPU-driven occlusion culling to sustain smooth frame pacing in complex scenes.

### 📦 Content & File Management
- **SAF Document Provider**: Direct read & write access for third-party file managers (`content://com.goydevv.horizon.documents`).
- **One-Tap Folder Import**: Import custom worlds, resource packs, and shader packs directly from phone storage.
- **Zip Folder Export**: Compress and export any folder directly through Android's system share/file picker.
- **Sandboxed Modding**: Support for native `.hmod` sandboxed content packages.

---

## Building from Source

### Prerequisites
- **Android SDK** (API 35, Build-Tools 35.0.0+)
- **Android NDK** (28.2.13676358 / r28+)
- **Rust Toolchain** (1.90+ with `aarch64-linux-android` and `armv7-linux-androideabi` targets)
- **Java Development Kit** (JDK 17 or 21)
- **Python** (3.10+)

### Build APK
```sh
# Build ARM64 optimized APK
python3 tools/android_build.py --abi arm64-v8a --profile release

# Build ARMv7 32-bit APK
python3 tools/android_build.py --abi armeabi-v7a --profile release
```

The output APK will be generated under `packaging/android/build/outputs/apk/`.

For complete developer documentation, see [docs/android.md](docs/android.md).

---

## Contributing

Contributions, bug reports, and optimizations are welcome!
- Review [CONTRIBUTING_ANDROID.md](CONTRIBUTING_ANDROID.md) before opening a pull request.
- Run tests and self-checks:
  ```sh
  python3 -m unittest discover -s tests -p 'test_android*.py'
  python3 tools/check_public_tree.py
  ```

---

## License & Legal

- Code is licensed under the **[MIT License](LICENSE)**.
- N3xLauncher is based on [Horizon Android](https://github.com/GoyDevv/Horizon-Android) by GoyDevv. Keep the original copyright notice in [LICENSE](LICENSE).
- Minecraft is a trademark of Mojang Synergies AB. This project is not affiliated with, endorsed by, or associated with Mojang or Microsoft.
- No proprietary game assets, jars, or binary resources are stored within this repository.
