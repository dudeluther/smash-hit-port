Smash Hit - web share bundle
============================

Upload the CONTENTS of this folder to a GitHub repository (root, or a subfolder).
index.html is the page; it loads rexcomp.wasm.00/.01, manifest.json, image.bin and game/ from the same base URL.

1. The page is pinned to the jsDelivr copy of this repo with:
       <base href="https://cdn.jsdelivr.net/gh/dudeluther/smash-hit-port@main/">
   Change that line only if the repo or branch changes. If index.html is served beside the files
   and should use local assets instead, use <base href="./">.

2. Open the page over HTTP(S), for example:
   https://cdn.jsdelivr.net/gh/USER/REPO@main/index.html
   If jsDelivr returns the HTML as a download instead of a page, host index.html on GitHub Pages
   and point <base> at the jsDelivr copy of this folder.

3. Limits: the largest file is 19.9 MB (jsDelivr's per-file limit is 20 MB; GitHub allows 100 MB).
   Total bundle is about 100 MB. Keep the original filenames.

4. Must be served over HTTP(S): file:// pages cannot fetch the wasm parts or game data.

5. This is the cooperative build. The ?mt threaded module (rexcomp_mt.js/wasm) is not included.

Known limitations: music is silent (the lifted Vorbis DSP is broken, so streaming music is a silent WAV);
some level-transition visuals / black frames and shader glitches remain in this build.
