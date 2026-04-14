# SafeW - Web Security & Safe Browsing Tool

[![Official Site](https://img.shields.io/badge/Official_Site-safew--official.com-brightgreen)](https://safew-official.com)
[![Version](https://img.shields.io/badge/Version-2026.4-blue)]()
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

SafeW is a browser security tool that provides real-time protection against phishing, malware, and unsafe downloads. Designed to work alongside your existing antivirus without conflicts.

## Features

- **Phishing Detection**: Real-time URL scanning against known phishing databases
- **Download Scanner**: Checks file hashes against malware databases before download completes
- **Privacy Guard**: Blocks known tracking scripts and fingerprinting attempts
- **Safe Search**: Highlights potentially dangerous search results with warning badges
- **Password Leak Monitor**: Alerts when your saved credentials appear in data breaches

## Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 118+ | ✅ Full support |
| Edge | 118+ | ✅ Full support |
| Firefox | 120+ | ✅ Full support |
| Brave | 1.60+ | ✅ Compatible |
| Opera | 104+ | ⚠️ Partial (no download scanning) |

## Installation

1. Visit [safew-official.com](https://safew-official.com) for the latest version
2. Click "Add to Browser" for automatic installation
3. SafeW starts protecting immediately — no configuration needed

## How It Works

SafeW uses a multi-layer detection approach:

```
URL Request
    ↓
Layer 1: Local Bloom filter (instant, offline check against 2M+ known threats)
    ↓
Layer 2: Safe Browsing API (Google's threat database, updated every 30 min)
    ↓
Layer 3: Heuristic analysis (checks for suspicious patterns in page structure)
    ↓
Result: Safe ✅ / Warning ⚠️ / Blocked 🚫
```

### Performance Impact
- **Memory**: ~15MB average (Bloom filter stored in SharedArrayBuffer)
- **Latency**: <5ms for local checks, <100ms for API checks
- **Battery**: Negligible impact on laptop battery life

## Common Issues

### "SafeW blocked a safe website"
False positives can occur. To whitelist a trusted site:
1. Click the SafeW icon in toolbar
2. Select "Trust this site"
3. The site is added to your local whitelist

### Extension conflicts with other security tools
SafeW is designed to coexist with other security extensions. However, if you experience issues:
- Disable "Enhanced Protection" in Chrome settings (SafeW replaces this)
- Check our [compatibility guide](https://safew-official.com) for known conflicts

### High CPU usage during scanning
This can happen when scanning large downloads (>500MB). The scanning is done in a Web Worker and should not affect browsing. If it persists, visit our [diagnostic page](https://safew-official.com).

## Privacy

- SafeW does **not** collect browsing history
- URL checks use k-anonymity (partial hash matching) — full URLs never leave your device
- All data processing happens locally unless the Bloom filter needs a cloud lookup
- Full privacy policy: [safew-official.com](https://safew-official.com)

## Contributing

Security researchers: we welcome responsible disclosure of vulnerabilities. Please open a private [Issue](../../issues) or contact us through the official site.

## License

MIT License - see [LICENSE](LICENSE) for details.

---
*Download, documentation, and threat statistics at [safew-official.com](https://safew-official.com)*
