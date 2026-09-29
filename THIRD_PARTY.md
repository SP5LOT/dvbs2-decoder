# Third-party components

The receiver and MX Uploader are licensed under the GNU General Public License version 3 ([LICENSE](LICENSE)).
They use or ship the components below. Source code, including our patches to leansdr and to the LDPC tool (`engine/`), is in `SP5LOT-dvbs2-decoder-1.0.0-source.zip` on the [release page](../../releases).

| Component | License | Where it ends up | Source |
|---|---|---|---|
| **leansdr** (pabr, www.pabr.org), DVB-S2 demodulator and FEC | GNU GPL v3 or later | `leandvb_s2.exe` | https://github.com/pabr/leansdr, branch `work`, commit `84c59e1c7a1a79338d5722d63f28640cc9d350f3`, plus `engine/leansdr.diff` from the source ZIP |
| **LDPC tool** (Ahmet Inan, adapted by pabr) | permissive, see below | `ldpc_tool.exe` (AVX2), `ldpc_tool_v2.exe` (no AVX) | https://github.com/pabr/xdsopl-LDPC-pabr, branch `ldpc_tool`, commit `6ada4aac6d853835eeaefb7e12a0136481647b01`, plus `engine/xdsopl-ldpctool.diff` from the source ZIP |
| **ssdv** (Philip Heron), SSDV image decoder | GNU GPL v3 or later | compiled into `leandvb_gui.exe` | https://github.com/fsphil/ssdv |
| **Dear ImGui** (Omar Cornut and contributors) | MIT | compiled into both programs | https://github.com/ocornut/imgui |
| **GLFW** 3.4 | zlib/libpng | compiled into both programs | https://www.glfw.org |
| **stb_image** (Sean Barrett) | MIT or public domain (Unlicense), at your choice | compiled into `leandvb_gui.exe` | https://github.com/nothings/stb |
| **rtl-sdr** (Osmocom; the bundled DLL is a build of unverified origin) | GNU GPL v2 or later | `librtlsdr.dll` | https://gitea.osmocom.org/sdr/rtl-sdr |
| **libhackrf** (Great Scott Gadgets and contributors) | BSD 3-clause, see below | `libhackrf.dll` | https://github.com/greatscottgadgets/hackrf |
| **libusb** 1.0.23 | GNU LGPL v2.1 or later | `libusb-1.0.dll` | https://github.com/libusb/libusb |
| **MinGW-w64 winpthreads** | MIT and BSD-3-Clause-Clear (MSYS2 package license) | `libwinpthread-1.dll`, also compiled into both programs | https://www.mingw-w64.org |
| **GCC runtime** (libstdc++, libgcc) | GNU GPL v3 with the GCC Runtime Library Exception | compiled into both programs; `msys-stdc++-6.dll`, `msys-gcc_s-seh-1.dll` | https://gcc.gnu.org |
| **MSYS2 runtime** 3.6.5 (based on Cygwin) | GPL (MSYS2 package license) | `msys-2.0.dll` | https://github.com/msys2/msys2-runtime |
| **GNU bash** 5.3.9 (MSYS2 build) | GNU GPL v3 or later | `bash.exe` | https://www.gnu.org/software/bash/ and https://github.com/msys2/MSYS2-packages |
| **FFmpeg** (gyan.dev "full" build 2025-08-20, git 4d7c609be3) | GNU GPL v3 (`--enable-gpl --enable-version3`) | `ffmpeg.exe` | https://ffmpeg.org and https://www.gyan.dev/ffmpeg/builds/ |

Not included: VLC media player. If it is installed, the receiver uses its libVLC for the video preview.

## LDPC tool license

Full text of the file `LICENSE` in pabr/xdsopl-LDPC-pabr:

```
Copyright (C) 2018 by Ahmet Inan <xdsopl@gmail.com>

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```
## libhackrf license (BSD 3-clause)

Text of `host/libhackrf/src/hackrf.c` in hackrf release v2018.01.1 (the bundled DLL does not report its version and lacks functions added in 2021 and later):

```
Copyright (c) 2012, Jared Boone <jared@sharebrained.com>
Copyright (c) 2013, Benjamin Vernoux <titanmkd@gmail.com>
Copyright (c) 2013, Michael Ossmann <mike@ossmann.com>

All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

    Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
    Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the
	documentation and/or other materials provided with the distribution.
    Neither the name of Great Scott Gadgets nor the names of its contributors may be used to endorse or promote products derived from this software
	without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED.
IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
