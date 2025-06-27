mesa options
============

Infos copied from various places, built against current CRUX 3.7
Latest update: 07/20/2024, CRUX 3.7, mesa 24.1.4-2

*:
1. [meson.build · main · Mesa / mesa · GitLab](https://gitlab.freedesktop.org/mesa/mesa/-/blob/main/meson.build?ref_type=heads)
2. [meson_options.txt · main · Mesa / mesa · GitLab](https://gitlab.freedesktop.org/mesa/mesa/-/blob/main/meson_options.txt?ref_type=heads)
3. [BLFS: Mesa-23.1.8](https://www.linuxfromscratch.org/blfs/view/svn/x/mesa.html)
4. [File Mesa.spec of Package Mesa - openSUSE Build Service](https://build.opensuse.org/package/view_file/openSUSE:Factory/Mesa/Mesa.spec?expand=1)

See BLFS for a comprehensive rundown on what is needed when.

## cbindgen rust-bindgen
---
> 💡 **_NOTE:_**  Needs vulkan-loader installed.
---
Allows building the nouveau vulkan driver.
```
=======> New files found:
NEW       -rwxr-xr-x      root/root       usr/lib/libvulkan_nouveau.so
NEW       -rw-r--r--      root/root       usr/share/vulkan/icd.d/nouveau_icd.x86_64.json
=======> Building '/home/pkgmk/packages/mesa#24.1.4-2.pkg.tar.xz' succeeded.
```

## directx-headers

---
> 💡 **_NOTE:_**  Needs vulkan-loader installed for `microsoft-experimental`
> vulkan driver.
---

Allows building the d3d12 gallium driver, as well as the microsoft-experimental
vulkan driver.

```
=======> New files found:
NEW       drwxr-xr-x      root/root       usr/bin/
NEW       -rwxr-xr-x      root/root       usr/bin/spirv2dxil
NEW       -rwxr-xr-x      root/root       usr/lib/dri/d3d12_dri.so
NEW       -rw-r--r--      root/root       usr/lib/libspirv_to_dxil.a
NEW       -rwxr-xr-x      root/root       usr/lib/libspirv_to_dxil.so
NEW       -rwxr-xr-x      root/root       usr/lib/libvulkan_dzn.so
NEW       -rw-r--r--      root/root       usr/share/vulkan/icd.d/dzn_icd.x86_64.json
=======> Building '/home/pkgmk/packages/mesa#24.1.4-1.pkg.tar.xz' succeeded.
```

## glslang

---
> 💡 **_NOTE:_**  Needs vulkan-loader installed.
---

Allows building the amd vulkan driver, as well as the overlay vulkan layer.

```
=======> ERROR: Footprint mismatch found:
NEW       -r-xr-xr-x      root/root       usr/bin/mesa-overlay-control.py
NEW       -rwxr-xr-x      root/root       usr/lib/libVkLayer_MESA_overlay.so
NEW       -rwxr-xr-x      root/root       usr/lib/libvulkan_radeon.so
NEW       -rw-r--r--      root/root       usr/share/drirc.d/00-radv-defaults.conf
NEW       drwxr-xr-x      root/root       usr/share/vulkan/explicit_layer.d/
NEW       -rw-r--r--      root/root       usr/share/vulkan/explicit_layer.d/VkLayer_MESA_overlay.json
NEW       -rw-r--r--      root/root       usr/share/vulkan/icd.d/radeon_icd.x86_64.json
=======> ERROR: Building '/home/pkgmk/packages/mesa#24.1.4-1.pkg.tar.xz' succeeded.
```

## glslang libclc python3-ply lua

---
> 💡 **_NOTE:_**  Needs vulkan-loader installed.
---

Skylake or later vulkan drivers.

```
=======> New files found:
NEW       drwxr-xr-x      root/root       etc/
NEW       drwxr-xr-x      root/root       etc/OpenCL/
NEW       drwxr-xr-x      root/root       etc/OpenCL/vendors/
NEW       -rw-r--r--      root/root       etc/OpenCL/vendors/mesa.icd
NEW       drwxr-xr-x      root/root       usr/bin/
NEW       -r-xr-xr-x      root/root       usr/bin/mesa-overlay-control.py
NEW       -rwxr-xr-x      root/root       usr/lib/dri/iris_dri.so
NEW       drwxr-xr-x      root/root       usr/lib/gallium-pipe/
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_crocus.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_i915.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_iris.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_nouveau.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_r300.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_r600.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_radeonsi.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_swrast.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_vmwgfx.so
NEW       lrwxrwxrwx      root/root       usr/lib/libMesaOpenCL.so -> libMesaOpenCL.so.1
NEW       lrwxrwxrwx      root/root       usr/lib/libMesaOpenCL.so.1 -> libMesaOpenCL.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/libMesaOpenCL.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/libVkLayer_INTEL_nullhw.so
NEW       -rwxr-xr-x      root/root       usr/lib/libVkLayer_MESA_overlay.so
NEW       -rwxr-xr-x      root/root       usr/lib/libvulkan_intel.so
NEW       -rwxr-xr-x      root/root       usr/lib/libvulkan_radeon.so
NEW       -rw-r--r--      root/root       usr/share/drirc.d/00-radv-defaults.conf
NEW       drwxr-xr-x      root/root       usr/share/vulkan/explicit_layer.d/
NEW       -rw-r--r--      root/root       usr/share/vulkan/explicit_layer.d/VkLayer_INTEL_nullhw.json
NEW       -rw-r--r--      root/root       usr/share/vulkan/explicit_layer.d/VkLayer_MESA_overlay.json
NEW       -rw-r--r--      root/root       usr/share/vulkan/icd.d/intel_icd.x86_64.json
NEW       -rw-r--r--      root/root       usr/share/vulkan/icd.d/radeon_icd.x86_64.json
=======> Building '/home/pkgmk/packages/mesa#24.1.4-1.pkg.tar.xz' succeeded.
```

## libclc

Builds both the gallium "clover" frontend and iris driver (Broadwell and
later).

```
=======> New files found:
NEW       drwxr-xr-x      root/root       etc/
NEW       drwxr-xr-x      root/root       etc/OpenCL/
NEW       drwxr-xr-x      root/root       etc/OpenCL/vendors/
NEW       -rw-r--r--      root/root       etc/OpenCL/vendors/mesa.icd
NEW       -rwxr-xr-x      root/root       usr/lib/dri/iris_dri.so
NEW       drwxr-xr-x      root/root       usr/lib/gallium-pipe/
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_crocus.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_i915.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_iris.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_nouveau.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_r300.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_r600.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_radeonsi.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_swrast.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_vmwgfx.so
NEW       lrwxrwxrwx      root/root       usr/lib/libMesaOpenCL.so -> libMesaOpenCL.so.1
NEW       lrwxrwxrwx      root/root       usr/lib/libMesaOpenCL.so.1 -> libMesaOpenCL.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/libMesaOpenCL.so.1.0.0
=======> Building '/home/pkgmk/packages/mesa#24.1.4-1.pkg.tar.xz' succeeded.
```

## libclc rust-bindgen

Enables rusticl, another OpenCL implementation on top of the gallium drivers.

```
=======> New files found:
NEW       drwxr-xr-x      root/root       etc/
NEW       drwxr-xr-x      root/root       etc/OpenCL/
NEW       drwxr-xr-x      root/root       etc/OpenCL/vendors/
NEW       -rw-r--r--      root/root       etc/OpenCL/vendors/mesa.icd
NEW       -rw-r--r--      root/root       etc/OpenCL/vendors/rusticl.icd
NEW       -rwxr-xr-x      root/root       usr/lib/dri/iris_dri.so
NEW       drwxr-xr-x      root/root       usr/lib/gallium-pipe/
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_crocus.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_i915.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_iris.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_nouveau.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_r300.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_r600.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_radeonsi.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_swrast.so
NEW       -rwxr-xr-x      root/root       usr/lib/gallium-pipe/pipe_vmwgfx.so
NEW       lrwxrwxrwx      root/root       usr/lib/libMesaOpenCL.so -> libMesaOpenCL.so.1
NEW       lrwxrwxrwx      root/root       usr/lib/libMesaOpenCL.so.1 -> libMesaOpenCL.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/libMesaOpenCL.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/libRusticlOpenCL.so -> libRusticlOpenCL.so.1
NEW       lrwxrwxrwx      root/root       usr/lib/libRusticlOpenCL.so.1 -> libRusticlOpenCL.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/libRusticlOpenCL.so.1.0.0
=======> Building '/home/pkgmk/packages/mesa#24.1.4-2.pkg.tar.xz' succeeded.
```

## libunwind

Use libunwind for stack-traces.

## libva

VA-API support for various gallium drivers.

see BLFS about a circular dependency warning and how to handle it

```
=======> New files found:
NEW       -rwxr-xr-x      root/root       usr/lib/dri/nouveau_drv_video.so
NEW       -rwxr-xr-x      root/root       usr/lib/dri/r600_drv_video.so
NEW       -rwxr-xr-x      root/root       usr/lib/dri/radeonsi_drv_video.so
NEW       -rwxr-xr-x      root/root       usr/lib/dri/virtio_gpu_drv_video.so
=======> Building '/home/pkgmk/packages/mesa#24.1.4-2.pkg.tar.xz' succeeded.
```

## libvdpau

Video Decode and Presentation API for Unix developed by NVIDIA. Might be
obsolete by now.

```
=======> New files found:
NEW       drwxr-xr-x      root/root       usr/lib/vdpau/
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_nouveau.so -> libvdpau_nouveau.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_nouveau.so.1 -> libvdpau_nouveau.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_nouveau.so.1.0 -> libvdpau_nouveau.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/vdpau/libvdpau_nouveau.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_r600.so -> libvdpau_r600.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_r600.so.1 -> libvdpau_r600.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_r600.so.1.0 -> libvdpau_r600.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/vdpau/libvdpau_r600.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_radeonsi.so -> libvdpau_radeonsi.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_radeonsi.so.1 -> libvdpau_radeonsi.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_radeonsi.so.1.0 -> libvdpau_radeonsi.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/vdpau/libvdpau_radeonsi.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_virtio_gpu.so -> libvdpau_virtio_gpu.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_virtio_gpu.so.1 -> libvdpau_virtio_gpu.so.1.0.0
NEW       lrwxrwxrwx      root/root       usr/lib/vdpau/libvdpau_virtio_gpu.so.1.0 -> libvdpau_virtio_gpu.so.1.0.0
NEW       -rwxr-xr-x      root/root       usr/lib/vdpau/libvdpau_virtio_gpu.so.1.0.0
=======> Building '/home/pkgmk/packages/mesa#24.1.4-2.pkg.tar.xz' succeeded.
```

## lm_sensors

Enable HUD lmsensors support.

## vulkan-loader

Needed for the zink gallium driver. Also needed to build any vulkan driver.

```
=======> ERROR: Footprint mismatch found:
NEW       -rwxr-xr-x      root/root       usr/lib/dri/zink_dri.so
=======> Building '/home/pkgmk/packages/mesa#24.1.4-2.pkg.tar.xz' succeeded.
```

## wayland-protocols

Build support for the  wayland window system.
