<div align="center">

# Nebula.NET

### Professional .NET obfuscation & code hardening — by [Delta1 Labs](https://delta1labs.com)

Protect your .NET assemblies from reverse engineering — without changing how they run.

[**Download**](https://github.com/Delta1-labs/nebula-releases/releases/latest) ·
[Website](https://delta1labs.com) ·
[Docs](https://delta1labs.com/docs/nebula/getting-started) ·
[Pricing](https://delta1labs.com/pricing) ·
[Editions](./EDITIONS.md)

</div>

---

This repository hosts the **official Windows installers** for Nebula.NET. The product source is private; this repo is for distribution, the license agreement, and release notes.

## What is Nebula.NET?

.NET compiles to IL, which decompilers (ILSpy, dnSpy, dotPeek) turn back into near-original C# in seconds. Nebula.NET rewrites that IL so it's genuinely hard to read and tamper with, while producing output that behaves **identically** to your original build.

- **Identifier renaming** — with public-API, reflection and serialization preservation
- **Control-flow flattening** — real dispatcher state machines, not just reordering
- **String encryption** — fresh per-build key, unbranded inlined decryptor
- **Anti-tamper & anti-debug** — configurable reactions
- **Resource & metadata hardening**, **Authenticode signing**
- **Stack-trace de-obfuscation** — translate obfuscated crash traces back with symbol maps
- **Enterprise:** per-customer **watermarking** (leak tracing) + aggressive control-flow

Runs on **.NET Framework 4.8** and **.NET 6, 8, 9, 10** (Windows 10/11), via a **command line**, a **desktop GUI**, and **MSBuild/CI**.

## Download & install

1. Grab the latest **`Nebula.NET-Setup-x.y.z.exe`** from [Releases](https://github.com/Delta1-labs/nebula-releases/releases/latest) (a raw `.msi` is also provided for managed deployments).
2. Run it — it installs the `nebula` CLI and the desktop GUI. No .NET runtime required on the target.

> Newly released installers are unsigned and may trigger a SmartScreen/antivirus reputation prompt; reputation builds over time. Always download from this Releases page or from delta1labs.com.

## Quick start

```bash
# nebula.config.json next to your build output:
# {
#   "schemaVersion": 1,
#   "inputs": ["bin/Release/net8.0/MyApp.dll"],
#   "outputDirectory": "protected",
#   "preservePublicApi": true,
#   "encryptStrings": true,
#   "controlFlowObfuscation": true
# }

nebula --config nebula.config.json
```

Then run your tests against the `protected/` build to confirm identical behavior. Full guide: **https://delta1labs.com/docs/nebula/getting-started**

## Editions & pricing

Free, Licensed ($199/seat/yr or $796 perpetual), and Enterprise. See **[EDITIONS.md](./EDITIONS.md)** for the full comparison, or [delta1labs.com/pricing](https://delta1labs.com/pricing).

Activate a purchased key:
```bash
nebula register --key LIC-XXXXXXXXXXXX
nebula license      # shows your edition
```

## Links

- 📄 **License:** [EULA.md](./EULA.md)
- 📝 **Changelog:** [CHANGELOG.md](./CHANGELOG.md)
- 📚 **Documentation:** https://delta1labs.com/docs
- ✉️ **Support:** support@delta1labs.com · **Sales:** sales@delta1labs.com

---

<div align="center">
© Delta1 Labs · Nebula.NET is proprietary software licensed under the <a href="./EULA.md">EULA</a>.
</div>
