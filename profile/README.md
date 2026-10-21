<p align="center">
  <a href="https://kryptic.dev">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="banner-dark.png">
      <img alt="Kryptic. Zero-friction secrets for developers." src="banner-light.png">
    </picture>
  </a>
</p>

<p align="center">
  <a href="https://kryptic.dev">Website</a>
  &nbsp;·&nbsp;
  <a href="https://docs.kryptic.dev">Docs</a>
  &nbsp;·&nbsp;
  <a href="https://kryptic.dev/download">Download</a>
  &nbsp;·&nbsp;
  <a href="https://app.kryptic.dev">App</a>
  &nbsp;·&nbsp;
  <a href="https://kryptic.dev/security">Security</a>
</p>

Kryptic replaces `.env` files and CLI wrappers with a background daemon. Sign in once with Google, Microsoft, or GitHub, then press run. Secrets arrive over a local socket for .NET, Node.js, Python, Java, Go, Ruby, C++, and Rust.

The repo commits a project ID. No tokens, no credentials. Values live in daemon memory, and the platform stores ciphertext it cannot open. Decryption happens on your laptop, in your browser, or on a CI runner that holds a sealed grant.

## Install, then run

Windows, macOS, and Linux builds are on [kryptic.dev/download](https://kryptic.dev/download). On Linux:

```bash
curl -fsSL https://kryptic.dev/install.sh | sh
kryptic login
```

Add the SDK for your language and commit `kryptic.json`. Then F5, `npm run dev`, or `dotnet run`. No wrapper command.

```json
{
  "projectId": "proj_a1b2c3d4e5f6",
  "defaultEnvironment": "development"
}
```

## Language clients

Apache-2.0. Each package asks the local daemon for the current project's secrets at startup. If the daemon is not running, the app still starts with the environment it already has.

<table>
  <tr>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Net"><b>.NET</b></a></td>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Node"><b>Node.js</b></a></td>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Python"><b>Python</b></a></td>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Java"><b>Java</b></a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Go"><b>Go</b></a></td>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Ruby"><b>Ruby</b></a></td>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Cpp"><b>C++</b></a></td>
    <td align="center"><a href="https://github.com/dev-kryptic/Kryptic.Rust"><b>Rust</b></a></td>
  </tr>
</table>

## Also in this org

The daemon is GPL-3.0. The encryption engines and the Kubernetes operator are Apache-2.0. Encryption is AES-256-GCM, sealed boxes, and Argon2id.

| Repository | What it does |
| --- | --- |
| [Kryptic.Daemon](https://github.com/dev-kryptic/Kryptic.Daemon) | Desktop daemon, CLI, and tray. One sign-in, then every SDK on the machine reads secrets from a local socket. |
| [Kryptic.K8s.Operator](https://github.com/dev-kryptic/Kryptic.K8s.Operator) | Syncs a Kryptic project into a native Kubernetes Secret. The operator decrypts inside the cluster. |
| [Kryptic.Encryption.Net](https://github.com/dev-kryptic/Kryptic.Encryption.Net) | Encryption engine for .NET. |
| [Kryptic.Encryption.Go](https://github.com/dev-kryptic/Kryptic.Encryption.Go) | Encryption engine for Go. |
| [Kryptic.Encryption.NPM](https://github.com/dev-kryptic/Kryptic.Encryption.NPM) | Encryption engine for TypeScript, on WebCrypto. |
| [Kryptic.Docs](https://github.com/dev-kryptic/Kryptic.Docs) | Documentation published at [docs.kryptic.dev](https://docs.kryptic.dev). |
| [Kryptic.All.Language.Packages.Tester](https://github.com/dev-kryptic/Kryptic.All.Language.Packages.Tester) | Integration runners for the daemon, the socket, the packages, and the process environment. |

## Security

Email vulnerabilities to **security@kryptic.dev**. Do not open a public issue. Policy: [kryptic.dev/security/disclosure](https://kryptic.dev/security/disclosure).
