# Self Presentation

A one-page, zero-dependency site documenting a private home AI stack:

- **NVIDIA DGX Spark** — GB10 Grace Blackwell inference server running a custom
  serving stack (recipe V5) with `qwen3.8-flash-next`, 128 GB unified memory
- **NVIDIA Jetson Orin Nano** — always-on agent host running Hermes Agent
  (sessions, memory, tools, cron) — the single stateful box
- **WireGuard (`wg-orin`)** — the inference API never leaves the LAN
- **Many doors, one brain** — an interactive animated pipeline diagram shows
  a message traveling from Telegram (phone), a desktop app over an SSH tunnel,
  or a plain SSH terminal to the same agent and the same session store

All performance figures on the page (RTT, TTFT, prefill/cache behavior, idle
power draw) were measured on the live machines, not quoted from vendor sheets.

## Structure

```
index.html   # the entire site — one static file, NVIDIA-flavored design system,
             # vanilla-JS interactive topology (packet animation, event log,
             # clickable nodes, cache warm/cold toggle)
```

No build step, no framework, no external JS. Fonts load from Google Fonts.
`prefers-reduced-motion` is respected.

## Local preview

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

GitHub Pages: Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)`.

## License

MIT
