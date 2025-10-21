# 🧠 Zama Developer Contributions Summary

Bu repo, Zama FHEVM ekosistemine hızlı onboarding ve görünür katkıların (commits) sağlanması için tasarlanmış bir Hardhat + TypeScript başlangıç projesidir.

## 🔹 Repository Setup
- Hardhat + TypeScript + Prettier + ESLint + CI (GitHub Actions)
- Zama Devnet ağına bağlanacak şekilde yapılandırılmış (`chainId: 9000`, RPC: `https://devnet.zama.ai`, sembol: `ZAMA`)
- Tutorial: "Hello FHEVM" – şifreli veriyi temsil eden basit bir kontrat ve etkileşim scriptleri

## 🔹 Kurulum
Ön koşullar: Node.js 18+ (veya 20+), npm

```bash
npm install
cp .env.example .env
# .env içine PRIVATE_KEY ve gerekirse TESTNET_RPC_URL ekleyin
```

## 🔹 Ağ Yapılandırması
`hardhat.config.ts` Zama Devnet'e bağlanacak şekilde ayarlanmıştır:
- `TESTNET_RPC_URL` varsayılan: `https://devnet.zama.ai`
- `chainId`: `9000`
- `PRIVATE_KEY`: Zama Devnet üzerinde işlem göndermek için cüzdan private key'i

MetaMask ağı ekleme (manuel):
- RPC: `https://devnet.zama.ai`
- Chain ID: `9000`
- Sembol: `ZAMA`

## 🔹 Komutlar
Test, deploy ve etkileşim komutları:
```bash
npm run test            # Hardhat testleri
npm run deploy:zama     # Zama ağına deploy (env'den PRIVATE_KEY alınır)
npm run interact:zama   # Kontratla basit etkileşim
```

Deploy sonrası adres `deployments/zama.json` içine yazılır. İsterseniz `.env` içine `CONTRACT_ADDRESS` koyarak `interact.ts` onu da kullanabilir.

## 🔹 Tutorial İçeriği
- Kontrat: `contracts/EncryptedHello.sol` – bytes türünde “şifreli” veriyi saklar
- Scriptler: `scripts/deploy.ts`, `scripts/interact.ts`
- Testler: `test/EncryptedHello.spec.ts`

Not: Bu örnek FHEVM davranışını **temsili** olarak gösterir. Gerçek FHE işlemleri için Zama FHEVM dokümanlarına ve ilgili kütüphanelere başvurun.

## 🔹 CI/CD
`.github/workflows/ci.yml` ile:
- `npm ci`, `lint`, `typecheck`, `test` aşamaları çalışır
- Secrets kontrolü (örnek): `PRIVATE_KEY` ayarlanmış olmalı

## 🔹 Örnek Commit Mesajları
- `chore(ci): improve workflow with env checks`
- `fix(ci): resolve lint and typecheck issues`
- `security(ci): add GitHub secrets and validate RPC`
- `feat: build Hello FHEVM tutorial (contract + scripts)`
- `docs: update README with Zama Devnet setup`

## 🔹 Amaç
Bu repo ile şunları gösterebilirsiniz:
- Zama FHEVM geliştirme ortamına aşinalık
Added more details for developers.
- CI/CD optimizasyonu ve güvenlik pratikleri
- Zama ekosistemi için eğitim odaklı katkılar

## 🔹 İlgili
- Zama FHEVM Public Repo: https://github.com/zama-ai/fhevm
- Zama Devnet RPC: `https://devnet.zama.ai`
