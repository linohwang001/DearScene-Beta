# Third-party notices

DearScene uses FFmpeg for compatibility decoding and proxy generation when Windows cannot safely present a media file.

- Project: FFmpeg — https://ffmpeg.org/
- License: LGPL v2.1 or later for the bundled LGPL configuration
- Windows build project: https://github.com/BtbN/FFmpeg-Builds
- Fixed build release: https://github.com/BtbN/FFmpeg-Builds/releases/tag/autobuild-2026-08-20-13-45
- Bundled build: `ffmpeg-N-126229-gf101fce22d-win64-lgpl.zip`
- Fixed build download: https://github.com/BtbN/FFmpeg-Builds/releases/download/autobuild-2026-08-20-13-45/ffmpeg-N-126229-gf101fce22d-win64-lgpl.zip
- Downloaded archive SHA-256: `27f3c0d84d248339ca690f288567923379bb2700b368972d449a528987a4b86a`
- Bundled `ffmpeg.exe` SHA-256: `a9e67abd4687bd30bfda8dbf304661271894422d0fa5e69fd72a9b7a9095f29d`
- Corresponding FFmpeg source revision: `f101fce22d` — https://github.com/FFmpeg/FFmpeg/commit/f101fce22d

DearScene embeds the unmodified FFmpeg executable as a separate runtime resource. On first use it is extracted, together with `FFmpeg-LICENSE.txt` and this notice, to DearScene's local runtime folder. DearScene verifies the pinned SHA-256 before packaging, after extraction, and before use. A mismatch causes the local copy to be replaced from the verified embedded resource rather than executed.
