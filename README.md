# HomeServo Echo Updatekanal

Dieses Repository ist der signierte Updatekanal der HomeServo-Firmware für den Echo Show 5 (2. Gen., „cronos“), aufgebaut auf [TECHO5](https://github.com/HuskerMinion/techo5). Es enthält **keinen Quellcode des HomeServo-Produkts und keine Geheimnisse**. Es enthält nur:

- die Releases (unter „Releases“): `manifest.json`, `manifest.json.sig`, `echod-arm` und `rootfs-v<Basis>-homeservo.<N>.tar.gz`;
- den öffentlichen Vertrauensschlüssel `echo-kanal-vertrauen.pub` (ed25519, base64);
- die Lizenz- und Herkunftshinweise unter `LICENSES/`.

Eine HomeServo-Firmware folgt ausschließlich diesem Kanal:
`https://github.com/Dormin121/homeservo-echo-kanal/releases/latest/download`

Sie installiert ein Paket nur, wenn alle drei Bedingungen erfüllt sind:
- `manifest.json.sig` ist eine gültige Signatur dieses Schlüssels über die exakten Manifest-Bytes;
- das Manifest trägt die Kennung `homeservo.kennung = homeservo-techo5-cronos-1` und eine Version im Schema `vX.Y.Z.N` (Upstream-Basis + HomeServo-Revision);
- Größe und SHA-256 jeder Datei stimmen mit dem Manifest überein.

## Prüfen
Öffentlicher Schlüssel (SHA-256 der Schlüsselzeichenkette `a183ce91055c612c20a79e2cdbda0aff3521c18baee983414f4787a07cdd34c0`):

```
OFtswsZBvpOKKy7pcqn/rbjF42yJil4MAdVMgRqTTAI=
```

## Lizenzen und Herkunft
- **Daemon `echod`:** TECHO5 (MIT, `LICENSES/TECHO5-MIT.txt`), abgeleitet aus EchoLocal (MIT, `LICENSES/EchoLocal-MIT.txt`, Hinweise in `LICENSES/TECHO5-NOTICE.txt`). HomeServo-Anpassungen: Frischezusage für die Bildanzeige und dieser eigene signierte Updatekanal.
- **Root-Dateisystem:** das veröffentlichte TECHO5-Rootfs der jeweiligen Basis. Ersetzt sind darin nur der Daemon und die Release-Zeile. Es enthält Alpine-Linux-Pakete unter verschiedenen Lizenzen, darunter GPL-2.0, GPL-3.0 und LGPL-2.1.
- Jedes Release nennt in seinen Notizen die enthaltenen Pakete mit Version und Lizenz sowie die zugehörigen Quellen.
