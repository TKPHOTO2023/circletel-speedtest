# CircleTel Speed Test

A free, self-contained internet speed test tool for CircleTel — measures ping, jitter,
download and upload speed directly in the browser.

- `index.html` — the whole UI (styles, scripts inline, no build step, no dependencies).
- `api/speedtest/ping.js` — Vercel Edge function, tiny fast response for latency/jitter.
- `api/speedtest/download.js` — Vercel Edge function, streams uncompressible random bytes.
- `api/speedtest/upload.js` — Vercel Edge function, reads and counts uploaded bytes.

## Deploy to Vercel

1. Import this repo at https://vercel.com/new
2. No build command or environment variables are needed — Vercel detects the static
   `index.html` and the Edge functions in `api/` automatically.

## Notes

- Speeds are estimates and vary with network conditions, server load, and distance to
  the edge region serving the request.
- IP/ISP lookup on the results panel uses the free `ipapi.co` API and fails silently if
  unreachable — it's cosmetic only, not used in the speed calculation.
