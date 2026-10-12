# Self Presentation

A one-page, zero-dependency site documenting a private home AI stack:

- **NVIDIA DGX Spark** — GB10 Grace Blackwell inference server running a custom
  serving stack (recipe V5) with `qwen3.8-flash-next`, 128 GB unified memory
- **NVIDIA Jetson Orin Nano** — always-on agent host running Hermes Agent
- **WireGuard (`wg-orin`)** — the inference API never leaves the LAN
- **Telegram** — the only human-facing surface, allowlisted

All performance figures on the page (RTT, TTFT, prefill/cache behavior) were
measured on the live machines, not quoted from vendor sheets.

## Structure

```
index.html   # the entire site — one static file, NVIDIA-flavored design system
```

No build step, no framework, no external JS. Fonts load from Google Fonts.

## Local preview

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Any static host works. For GitHub Pages: Settings → Pages → Source:
*Deploy from a branch* → `main` / `/ (root)`.

## License

MIT
