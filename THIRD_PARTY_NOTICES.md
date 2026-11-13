# Thông báo thành phần bên thứ ba / Third-Party Notices

VietGame có đi kèm các phần mềm, thư viện và model của bên thứ ba dưới đây. Mỗi thành phần
giữ nguyên giấy phép của tác giả gốc. Toàn văn giấy phép nằm trong thư mục `licenses/`
(và trong chính thư mục của từng thành phần khi được cài).

VietGame includes the third-party software, libraries and models listed below. Each component
remains under its original license. Full license texts are in the `licenses/` folder (and in
each component's own folder after installation).

---

## 1. vg-chiaki (Remote Play PS5) — GNU AGPL-3.0

| | |
|---|---|
| Thành phần | `vg-chiaki.exe` (thư mục `resources/vg-chiaki`) |
| Giấy phép | GNU Affero General Public License v3.0, kèm ngoại lệ OpenSSL (`licenses/AGPL-3.0.txt`) |
| Dựa trên | libchiaki của **chiaki-ng** — https://github.com/streetpea/chiaki-ng (commit `43728af2e639fecb8a7af1cd68c29820a40de973`) |
| Mã nguồn tương ứng | https://github.com/ntphuc1910-cloud/vg-chiaki |

`vg-chiaki.exe` là một chương trình riêng, chạy như tiến trình độc lập; VietGame chỉ giao tiếp với
nó qua dòng lệnh và luồng dữ liệu (stdin/stdout). Bạn có quyền lấy, sửa và phân phối lại mã nguồn của
vg-chiaki theo AGPL-3.0. Nếu không tải được mã nguồn từ đường dẫn trên, hãy liên hệ tác giả VietGame
để được cung cấp, trong vòng 3 năm kể từ khi nhận bản phát hành.

`vg-chiaki.exe` is a separate program run as an independent process; VietGame only talks to it over
the command line and standard streams. You may obtain, modify and redistribute its source code under
AGPL-3.0 at the link above (or by request to the author for at least three years after receiving a release).

### Thư viện đi kèm vg-chiaki / Libraries shipped with vg-chiaki (bản dựng MSYS2 MinGW-w64)

| Tệp | Dự án | Giấy phép |
|---|---|---|
| libchiaki (liên kết tĩnh) | chiaki-ng | AGPL-3.0 + OpenSSL exception |
| nanopb (tĩnh) | nanopb | zlib |
| jerasure, gf-complete (tĩnh) | Jerasure / GF-Complete | BSD-3-Clause |
| libcrypto-3-x64.dll | OpenSSL 3 | Apache-2.0 |
| libevent-7.dll | libevent | BSD-3-Clause |
| libjson-c-5.dll | json-c | MIT |
| libminiupnpc.dll | miniupnpc | BSD-3-Clause |
| libnghttp2-14.dll | nghttp2 | MIT |
| libpsl-5.dll | libpsl | MIT |
| libssh2-1.dll | libssh2 | BSD-3-Clause |
| libz-1.dll, zlib1.dll | zlib | zlib |
| libwinpthread-1.dll | mingw-w64 winpthreads | MIT / BSD-3-Clause |
| libiconv-2.dll | GNU libiconv | LGPL-2.1-or-later |
| libintl-8.dll | GNU gettext (libintl) | LGPL-2.1-or-later |
| libidn2-0.dll | GNU libidn2 | LGPL-3.0-or-later / GPL-2.0-or-later |
| libunistring-5.dll | GNU libunistring | LGPL-3.0-or-later / GPL-2.0-or-later |

Các thư viện LGPL được liên kết động (DLL riêng); bạn có thể thay thế chúng bằng bản tương thích do
bạn tự dựng. Mã nguồn của các gói này có tại kho gói MSYS2: https://packages.msys2.org/ và
https://github.com/msys2/MINGW-packages (phiên bản cụ thể ghi trong tệp `PACKAGES.txt` của vg-chiaki
khi có).

The LGPL libraries are dynamically linked (separate DLLs) and may be replaced with compatible builds.
Their sources are available from the MSYS2 package repositories listed above.

---

## 2. Giọng đọc VieNeu-TTS (tải và cài riêng trong app khi người dùng chọn) / VieNeu-TTS voice engine (optional, installed on demand)

| Thành phần | Nguồn | Giấy phép |
|---|---|---|
| VieNeu-TTS (mã nguồn, `vieneu`, `apps`) | https://github.com/pnnbao97/VieNeu-TTS — tác giả Phạm Nguyễn Ngọc Bảo | Apache-2.0 |
| Model VieNeu-TTS v3 Turbo (ONNX, giọng mẫu) | https://huggingface.co/pnnbao-ump/VieNeu-TTS-v3-Turbo | Apache-2.0 |
| MOSS-Audio-Tokenizer-Nano (codec ONNX) | https://huggingface.co/OpenMOSS-Team — OpenMOSS Team | Apache-2.0 |
| sea-g2p (chuyển chữ sang âm vị) | https://pypi.org/project/sea-g2p/ | Apache-2.0 |
| Python 3.12 (python-build-standalone) | Python Software Foundation / Astral | PSF-2.0 (kèm `python/LICENSE.txt`) |
| uv | https://github.com/astral-sh/uv — Astral | MIT OR Apache-2.0 |
| Các gói Python khác (onnxruntime, numpy, gradio, librosa, …) | PyPI | Xem thư mục `*.dist-info` của từng gói trong thư mục cài VieNeu |

Theo yêu cầu của tác giả VieNeu-TTS: không dùng tính năng nhân bản giọng để giả mạo người thật khi
chưa được phép, lừa đảo hoặc tạo nội dung sai lệch. Giọng mẫu có sẵn được phép dùng cho nội dung thương mại.

As requested by the VieNeu-TTS authors: do not clone real people's voices without consent or use the
model to impersonate, defraud or produce misleading content.

Bản GPU (PyTorch CUDA) không nằm trong bộ cài; khi người dùng chọn GPU, VietGame tải PyTorch
(BSD-3-Clause) và thư viện NVIDIA CUDA (giấy phép NVIDIA) trực tiếp từ nguồn chính thức về máy người dùng.

---

## 3. Ứng dụng máy tính / Desktop app

| Thành phần | Giấy phép |
|---|---|
| Electron (và Chromium, Node.js) | MIT; Chromium kèm theo `LICENSES.chromium.html` trong thư mục cài |
| Tesseract.js, Tesseract OCR, dữ liệu ngôn ngữ tessdata | Apache-2.0 |
| React, React DOM | MIT |
| lucide-react (biểu tượng) | ISC |
| motion | MIT |
| Express, ws, dotenv, electron-updater | MIT / BSD-2-Clause |
| @google/genai | Apache-2.0 |
| msedge-tts | MIT |

Danh sách đầy đủ các gói npm đi kèm (tên, phiên bản, giấy phép) nằm trong `licenses/npm-packages.txt`;
toàn văn giấy phép của từng gói nằm trong thư mục `node_modules/<gói>` sau khi cài.

---

## 3b. Bản Android / Android app

| Thành phần | Giấy phép |
|---|---|
| Capacitor (Ionic) | MIT |
| @capawesome/capacitor-nodejs, Node.js for Mobile Apps | MIT |
| Node.js | MIT (kèm giấy phép các thành phần của Node.js) |
| vg-chiaki cho Android (`libvgchiaki.so`) | AGPL-3.0 — mã nguồn: https://github.com/ntphuc1910-cloud/vg-chiaki (quy trình `build-vg-chiaki-android.yml`) |
| OpenSSL, json-c, miniupnpc, curl, nanopb, Jerasure, GF-Complete (liên kết tĩnh trong vg-chiaki Android) | Apache-2.0, MIT, BSD-3-Clause, curl, zlib, BSD-3-Clause |
| Giọng đọc: TextToSpeech của Android (dịch vụ có sẵn trên máy) | Theo điều khoản của nhà cung cấp giọng đọc trên máy |

Toàn văn giấy phép trong app Android: mục `legal/` đi kèm giao diện.

---

## 4. Dịch vụ trực tuyến (không đi kèm, chỉ kết nối) / Online services (not bundled)

- Google Gemini API, Groq API: người dùng tự nhập khóa API của mình và chịu điều khoản của nhà cung cấp.
- Supabase (kho phụ đề dùng chung): chỉ dùng khóa công khai (publishable key); dữ liệu chia sẻ là bản dịch do người dùng đồng ý gửi lên.

---

## 5. Nhãn hiệu / Trademarks

PlayStation, PS5 và DualSense là nhãn hiệu của Sony Interactive Entertainment Inc. LG và webOS là nhãn hiệu
của LG Electronics Inc. Windows là nhãn hiệu của Microsoft Corporation. VietGame không liên kết với, không
được tài trợ hay xác nhận bởi các công ty này.

---

## Phụ lục: văn bản giấy phép ngắn / Appendix: short license texts

### MIT License

```
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the
following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial
portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT
LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO
EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE
USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### BSD 3-Clause License

```
Redistribution and use in source and binary forms, with or without modification, are permitted provided
that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the
   following disclaimer.
2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and
   the following disclaimer in the documentation and/or other materials provided with the distribution.
3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or
   promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A
PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
```

### zlib License

```
This software is provided 'as-is', without any express or implied warranty. In no event will the authors
be held liable for any damages arising from the use of this software.

Permission is granted to anyone to use this software for any purpose, including commercial applications,
and to alter it and redistribute it freely, subject to the following restrictions:

1. The origin of this software must not be misrepresented; you must not claim that you wrote the original
   software. If you use this software in a product, an acknowledgment in the product documentation would
   be appreciated but is not required.
2. Altered source versions must be plainly marked as such, and must not be misrepresented as being the
   original software.
3. This notice may not be removed or altered from any source distribution.
```

### ISC License

```
Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is
hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE
INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF
USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```

Toàn văn Apache-2.0, AGPL-3.0, GPL-2.0, GPL-3.0, LGPL-2.1, LGPL-3.0, MPL-2.0: xem thư mục `licenses/`.
