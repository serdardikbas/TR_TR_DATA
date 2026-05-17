# 🚜 Traktör Saha Asistanı | 拖拉机市场助手

Zoomlion Agriculture Turkey saha ekibi için geliştirilmiş mobil web uygulaması.  
2012–2025 yılları arasında Türkiye'nin 84 ilindeki traktör satış verilerini analiz eder ve Claude AI ile saha desteği sağlar.

---

## 🌐 Özellikler

- **84 il × 14 yıl** traktör kayıt verisi (428.000+ satır)
- Marka, model ve traktör tipi bazında sıralama
- Yıllık trend grafikleri
- **Claude AI asistanı** — pazar analizi, rakip karşılaştırması, strateji önerileri
- **Türkçe ↔ 中文** dil değiştirme
- Mobil-first tasarım (saha ekibi için optimize)
- Tamamen statik — backend gerekmez

---

## 🚀 GitHub Pages Kurulumu

### 1. Repo Oluştur

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/KULLANICI_ADI/REPO_ADI.git
git push -u origin main
```

### 2. GitHub Pages Aktifleştir

- Repo → **Settings** → **Pages**
- Source: **Deploy from a branch**
- Branch: `main` / `/ (root)`
- **Save** → `https://KULLANICI_ADI.github.io/REPO_ADI`

---

## 🚂 Railway Kurulumu (Statik)

### railway.json oluştur:

```json
{
  "$schema": "https://railway.app/railway.schema.json",
  "build": {
    "builder": "NIXPACKS"
  },
  "deploy": {
    "startCommand": "npx serve . -p $PORT",
    "restartPolicyType": "ON_FAILURE"
  }
}
```

### package.json oluştur:

```json
{
  "name": "traktor-saha-asistani",
  "version": "1.0.0",
  "scripts": {
    "start": "npx serve . -p ${PORT:-3000}"
  },
  "dependencies": {
    "serve": "^14.0.0"
  }
}
```

Sonra Railway'de GitHub repo'yu bağla ve deploy et.

---

## 🔑 Claude API Key

1. [console.anthropic.com](https://console.anthropic.com) adresinden API key alın
2. Uygulamada sağ üstteki 🔑 butonuna tıklayın
3. `sk-ant-...` ile başlayan key'i girin
4. Key yalnızca tarayıcıda (localStorage) saklanır

---

## 📁 Dosya Yapısı

```
tractor-app/
├── index.html          # Tek sayfalık uygulama
├── tractor_data.json   # 84 il × 14 yıl agregat veri (1.1 MB)
├── README.md
├── railway.json        # Railway deploy config (opsiyonel)
└── package.json        # Railway için (opsiyonel)
```

---

## 📊 Veri Kaynağı

Türkiye Cumhuriyeti traktör tescil kayıtları (2012–2025).  
428.762 satır kayıt → il/yıl/marka/model bazında agregat.

---

## 🏢 Geliştiren

Zoomlion Agriculture Turkey — Market Intelligence & Strategic Sales
