# SafeW - Secure Instant Messaging / 安全即时通讯

[![Official Site](https://img.shields.io/badge/Official_Site-safew--official.com-brightgreen)](https://safew-official.com)
[![Version](https://img.shields.io/badge/Version-2026.4-blue)]()
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

In the digital age, your communication security matters more than ever. SafeW is a highly secure instant messaging application designed for users and enterprises who prioritize privacy above all else. Built on Telegram's end-to-end encryption technology, SafeW ensures your conversations are fully encrypted in transit — only the participants can access the message content.

## Core Features

- **End-to-End Encryption**: Based on Telegram's MTProto 2.0 protocol, all messages are encrypted before leaving your device
- **Private Deployment**: Self-host SafeW on your own infrastructure for complete data sovereignty
- **Self-Destructing Messages**: Set auto-delete timers from 1 second to 1 week
- **Secret Chats**: Device-specific encryption that leaves no trace on servers
- **Encrypted File Transfer**: Send documents, images, and videos with full encryption (up to 2GB per file)
- **Multi-Device Sync**: Securely sync across phone, tablet, and desktop with per-device encryption keys

## Platform Support

| Platform | Version | Status |
|----------|---------|--------|
| Android | 8.0+ | ✅ Full support |
| iOS | 14+ | ✅ Full support |
| Windows | 10+ | ✅ Desktop client |
| macOS | 12+ | ✅ Desktop client |
| Linux | Ubuntu 20.04+ | ✅ Desktop client |
| Web | Chrome/Edge/Firefox | ✅ Web client |

## Why SafeW?

### vs. Standard Messaging Apps

| Feature | SafeW | WhatsApp | Telegram | Signal |
|---------|-------|----------|----------|--------|
| End-to-End Encryption | ✅ All chats | ✅ All chats | ⚠️ Secret chats only | ✅ All chats |
| Private Deployment | ✅ | ❌ | ❌ | ❌ |
| No Phone Number Required | ✅ | ❌ | ❌ | ❌ |
| Open Source Client | ✅ | ❌ | ✅ Partial | ✅ |
| Max File Size | 2 GB | 2 GB | 2 GB | 100 MB |
| Self-Destructing Messages | ✅ | ✅ | ✅ | ✅ |
| Server-side Data Retention | Zero (private deploy) | Metadata stored | Messages stored | Minimal |

### Private Deployment Advantage

SafeW's most distinctive feature is **private deployment support**. Organizations can:

1. Host the entire SafeW server stack on their own infrastructure
2. All messages, files, and metadata stay within your network
3. No third-party can access, subpoena, or leak your communications
4. Full audit control over encryption keys and user management

This makes SafeW ideal for:
- **Enterprises** with strict data compliance requirements (GDPR, HIPAA)
- **Government agencies** handling classified communications
- **Journalism and activism** in sensitive environments
- **Healthcare providers** needing HIPAA-compliant messaging

## Encryption Technical Details

### Protocol Stack

```
Application Layer (message content)
    ↓
SafeW Encryption Layer (AES-256-IGE + SHA-256 HMAC)
    ↓
MTProto 2.0 Transport (Diffie-Hellman key exchange)
    ↓
TLS 1.3 (transport security)
    ↓
Network Layer
```

### Key Exchange Process

1. **Initial Handshake**: Client generates a 2048-bit RSA key pair
2. **DH Key Exchange**: Diffie-Hellman parameters negotiated with server
3. **Session Key**: 256-bit AES session key derived from shared secret
4. **Perfect Forward Secrecy**: Session keys rotated every 100 messages or 1 hour

### Secret Chat Encryption

Secret Chats use an additional layer:
- Device-to-device encryption (server cannot decrypt)
- Visualization of encryption key fingerprint for manual verification
- Screenshot detection and notification
- No message forwarding allowed

## Installation

### Personal Use
1. Visit [safew-official.com](https://safew-official.com) to download for your platform
2. Create an account (no phone number required — email or username only)
3. Start messaging securely

### Enterprise / Private Deployment
1. Visit [safew-official.com](https://safew-official.com) for deployment documentation
2. Minimum server requirements: 4 vCPU, 8GB RAM, 100GB SSD
3. Docker-based deployment with `docker-compose up`
4. Configure DNS, TLS certificates, and admin panel

## Common Issues

### Messages not delivering
Check your network connection. SafeW requires port 443 (HTTPS) to be open. Some corporate firewalls may block the MTProto protocol. Try enabling "TCP Fallback Mode" in Settings → Network.

### Encryption key verification failed
This occurs when a contact re-installs SafeW or switches devices. The encryption keys are regenerated for security. You'll see a notification — verify the new key fingerprint with your contact through a separate channel.

### Private deployment sync issues
Ensure all server nodes have synchronized clocks (NTP). Clock drift >5 seconds causes authentication failures between federated nodes.

For more troubleshooting, visit [safew-official.com](https://safew-official.com).

## Frequently Asked Questions

**Q: Can SafeW be wiretapped?**
A: With end-to-end encryption enabled, messages cannot be intercepted or read by anyone — including SafeW servers (or your own servers in private deployment). Only the sender and recipient hold the decryption keys.

**Q: What happens if I lose my device?**
A: Secret Chat messages exist only on the paired devices and cannot be recovered. Regular encrypted messages can be restored from the server (or your private server) after re-authentication.

**Q: Is SafeW free?**
A: The personal version is free. Enterprise private deployment requires a license — see [safew-official.com](https://safew-official.com) for pricing.

**Q: How does SafeW compare to Signal?**
A: Both offer strong encryption. SafeW's key differentiator is **private deployment** — Signal requires using Signal's servers, while SafeW lets you host everything yourself.

## Contributing

Security researchers are welcome to review our encryption implementation. Responsible disclosure via [Issues](../../issues) or through the official site.

## License

MIT License - see [LICENSE](LICENSE) for details.

---
*Download, enterprise deployment guide, and security documentation at [safew-official.com](https://safew-official.com)*

## Related Projects
- [KuaiLian VPN](https://github.com/mojinmopin-art/kuailian-vpn-client) - Secure VPN connection tool
- [QClaw AI](https://github.com/mojinmopin-art/qclaw-ai-assistant) - AI chat assistant for WeChat and QQ
- [OpenClaw AI](https://github.com/mojinmopin-art/openclaw-ai-assistant) - AI browser assistant
