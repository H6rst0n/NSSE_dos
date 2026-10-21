# Third-party software

## Original NSSE distribution

The 22 files in `reference_NSSE/` were supplied by the project owner. They are bundled unchanged in `assets/nsse.zip`; SHA-256 checksums are recorded in `assets/original-files.json`.

The original program identifies Frank Rioux, St. John's University, and Journal of Chemical Education: Software, Volume IIIB, Number 2, October 1990. Its opening screen displays copyright 1990 by the Division of Chemical Education of the American Chemical Society. Original notices are retained in the running program. No license granting public redistribution was found in the supplied directory. This browser wrapper does not relicense those original files.

## js-dos and DOSBox

Runtime: js-dos 6.22.60, with the matching WebAssembly DOSBox build supplied by the upstream v6.22 distribution. Downloaded 2026-10-21. Unmodified vendored files are listed in `vendor/js-dos/checksums.json`.

- Distribution: https://v8.js-dos.com/v6.22/js-dos.js
- Engine glue: https://v8.js-dos.com/v6.22/wdosbox.js
- WebAssembly binary (the upstream filename ends in .js): https://v8.js-dos.com/v6.22/wdosbox.wasm.js
- js-dos source / v6.22 branch: https://github.com/caiiiycuk/js-dos/tree/6.22
- DOSBox port source and build instructions: https://github.com/js-dos/dosbox
- Upstream API documentation: https://js-dos.com/6.22/docs/

GPL license texts are included as `vendor/js-dos/LICENSE` and `vendor/js-dos/DOSBOX-COPYING`. js-dos build metadata: version `6.22.60 (c3627d34f97fcc6e98ceef7fbea6e090)`; build seed `1622012539860`; wasm version `df90df0fd894cf6ee026bf847969c3ce`. Source map: https://v8.js-dos.com/v6.22/js-dos.js.map .

The wrapper does not load analytics, advertisements, cloud saves or external runtime URLs. Links above are provenance references, not runtime requests.

## Offline single-file edition

`NSSE.html` embeds the same vendor code, WebAssembly bytes and original ZIP. The engine is compiled from the embedded bytes; the original ZIP is extracted from a temporary in-memory Blob. No server or Internet request is required. This notice and both GPL license texts are embedded in the HTML template with ID `third-party-notices`.
