# Test Report: AMD Radeon RX 6600M + Ryzen 7 5800H (KLBF Lab & VIctory)

## Hardware & Environment Specs
- **CPU:** AMD Ryzen 7 5800H (8 Cores / 16 Threads)
- **GPU:** AMD Radeon RX 6600M (8 GB VRAM, RDNA2 Architecture)
- **RAM:** 16 GB DDR4
- **OS:** Windows 11 / 10 x64
- **Driver:** AMD Software: Adrenalin Edition
- **Target Title:** Grand Theft Auto VI (Xbox Series X|S Scarlett Dump)

## Performance & Stability Summary
- **Boot & Menus:** Boots cleanly at **30.0 FPS** (33.3 ms/frame, ~0.4 ms GPU time).
- **World Rendering:** Operates with AMD FSR upscaling (`--console series-s` 720p -> 1080p).
- **Session Duration:** **74+ minutes continuous run** achieved without crashes.
- **Memory & GPU:** **0x8007000E (E_OUTOFMEMORY)** and **DXGI_ERROR_DEVICE_HUNG** completely eliminated using `$env:VICTORY_CARD_BUFFERS_MB="256"`, `$env:VICTORY_FILL_WORKERS="4"`, and skipping unstable compute pipelines.

## Tested Environment Flags
```powershell
$env:VICTORY_SHADER_OPT="0"
$env:VICTORY_SKIP_PIPELINES=(Get-Content docs\klbf\skip-amd.txt -Raw).Trim()
$env:VICTORY_LATE_WAIT="1"
$env:VICTORY_WIDE_BACK="1"
$env:VICTORY_PIPELINE_WAIT_MS="24"
$env:VICTORY_RELAY_COPY_QUEUE="0"
$env:VICTORY_FFX_DIR="C:\FidelityFX-SDK\Kits\FidelityFX\signedbin"
```
