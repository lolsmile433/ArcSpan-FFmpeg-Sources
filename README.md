# ArcSpan FFmpeg Sources

Third-party FFmpeg source materials and build scripts prepared for ArcSpan Studio releases. This repository does not contain proprietary ArcSpan application source.

## Current status

**The verified source-hosting release for ArcSpan Studio 4.23.0-beta.1 is an unpublished draft prepared for final owner approval. Installer publication and patent clearance remain separate decisions.** Public users cannot download draft assets. No ArcSpan installer is distributed by this repository.

Planned source release tag: `v4.23.0-beta.1-ffmpeg-btbn-2026-11-13`.

The [release area](https://github.com/lolsmile433/ArcSpan-FFmpeg-Sources/releases) will hold version-specific source assets after verification and explicit owner approval. GitHub's automatic repository-source ZIP is not the FFmpeg source distribution.

## Preserved source components

- FFmpeg core snapshot: `d838f9f9aeb0e09b4d068e2af20a46a12640696f`.
- BtbN / FFmpeg-Builds scripts snapshot: `c9fe5114060e507409f7ee07edfd82efaf25d767`.
- Dependency cache split into `download-cache.zip.001` through `.009`.
- Reassembly helper, checksums, dependency manifest and source instructions.

These materials target upstream [autobuild-2026-11-13-12-43](https://github.com/FFmpeg-Builds/FFmpeg-Builds/releases/tag/autobuild-2026-11-13-12-43), specifically `ffmpeg-n9.0.2-57-gd838f9f9ae-win64-gpl-9.0.zip`. They must not be assumed to match another provider's or build's executables.

## Reassembly after publication

Download all nine numbered cache parts and the accompanying `Reassemble-Source.bat`, `README_Source_Download.txt` and `SHA256SUMS.txt` from the same release, preserving filenames. Inspect and run the batch file on Windows. It refuses to overwrite an existing output and checks the reconstructed SHA-256.

Expected `download-cache.zip`:
- Size: **2,243,238,945 bytes**.
- SHA-256: `17c490649c9358294ddf618e71cc91011ca11e189dbf5e3c9032b7a34f25ba07`.

The ZIP contains `cache.tar.gz`; its `.cache/downloads/` directory includes 129 dependency archives and 129 relative aliases. Preserve symlinks when restoring it in a tar-capable environment. Download the separate FFmpeg and build-script ZIPs too: the cache alone is not complete corresponding source.

## Verification so far

All 20 draft assets report uploaded. The nine cache-part sizes and GitHub digests match the independently checked originals and manifest. Reassembly, outer ZIP CRC, all 129 dependency archive hashes, XZ integrity, inner tar listings and aliases passed. The reassembly helper was reviewed and its digest matches the uploaded file.

Both exact-commit source ZIPs are now independently verified: hashes match the existing draft assets; ZIP CRC tests passed; all 10,424 FFmpeg files and 294 build-script files match the pinned upstream Git blobs with no missing or unexpected files. Executable bits match. A local configuration-generation test selected 97 dependency cache archives, all present under the required hashed filenames. The owner reports the replacement installer and installed executable correspondence tests complete, with all six FFmpeg legal files installed. The [historical source/build record and release decision](BUILDING-2026-11-13.md) document exact source selection, the tested snapshot-pinning adaptation, copyright notice findings and reproducibility limits. Source publication and anonymous access checks remain pending. No patent or general legal clearance is declared.

## Licensing

FFmpeg's pinned GPL build configuration enables GPL and version 3; preserve its license texts, including `COPYING.GPLv3`, and all applicable component notices. BtbN build scripts carry their own MIT license. Dependency sources retain their own licenses and copyright holders; this repository does not relicense every component under a blanket license. Some notices reside in source headers.

LCEVCdec's BSD-3-Clause-Clear notice expressly excludes patent grants and must be retained; applicable obligations for the actual binary require review.

See [FFmpeg licensing information](https://ffmpeg.org/legal.html) and [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html). A source hosting location alone does not establish redistribution compliance.
