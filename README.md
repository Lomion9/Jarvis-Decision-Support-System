# ⚓ Project JARVIS: Bitcoin (BTC) Derivatives & Sentiment Engine

**Project JARVIS**, Bitcoin (BTC) piyasalarındaki manipülatif hareketleri, likidite tuzaklarını ve trend dönüşlerini tespit etmek için tasarlanmış; **Türev Piyasa Verilerini (Derivatives Data)** ve **Zincir-Üstü (On-Chain) Metrikleri** işleyen gelişmiş bir algoritmik sistemdir.

Nasdaq için geliştirilen "Alice" projesinin kardeş modülü olan Jarvis, kripto piyasasının yüksek volatilitesine uyum sağlamak için özel bir **"Fisherman" (Balıkçı)** motoruna sahiptir.

## 🦈 "The Fisherman" Modülü (Unique Feature)

Jarvis'i diğer indikatörlerden ayıran en büyük özellik, fiyatın kendisine değil, **paranın nerede toplandığına** bakmasıdır.

* **Multi-Exchange Aggregation:** Binance, OKX ve Bybit borsalarından anlık `Funding Rate` (Fonlama Oranı) ve `Open Interest` (Açık Pozisyon) verilerini çeker.
* **Weighted Analysis (Ağırlıklı Analiz):** Borsaların hacmine göre verilere ağırlık verir. (Örn: Binance verisi, sinyali OKX'ten daha fazla etkiler).
* **Trap Detection (Tuzak Tespiti):**
    * *Fiyat Yükseliyor + OI Yükseliyor + Funding Aşırı Pozitif* = **Long Squeeze (Boğa Tuzağı)** riski. Jarvis puan kırar.
    * *Fiyat Düşüyor + OI Yükseliyor + Funding Negatif* = **Short Squeeze** potansiyeli. Jarvis alım fırsatı kollar.

## 🧠 Nasıl Çalışır?

Bu proje, **"Hybrid Intelligence"** (İnsan Deneyimi + AI Kodlama) yaklaşımıyla geliştirilmiştir:

### 1. Piyasa Konteksti (Crypto Context) 🌐
İşlem açmadan önce "Dominans" ve "Para Akışı"nı kontrol eder:
* **BTC.D & USDT.D:** Paranın Bitcoin'e mi yoksa stabil coinlere (nakite) mi aktığını analiz eder.
* **TOTAL3:** Altcoin piyasasının genel sağlığını kontrol eder.
* **Correlation:** SPX (Amerikan Borsaları) ile korelasyon bozulursa (Decoupling) stratejiyi buna göre adapte eder.

### 2. Akıllı Puanlama (Smart Scoring) 💯
Jarvis, her mum için 0-150 arasında bir puan üretir. Sinyal oluşması için teknik ve temel verilerin "Confluence" (Kesişim) sağlaması gerekir:
* **Fisherman Onayı:** Fonlama oranları nötr veya lehimize mi?
* **SMC (Smart Money Concepts):** Fiyat bir "Order Block" içinde mi? "Fair Value Gap" (FVG) dolduruldu mu?
* **Volatilite:** Volumatic VIDYA ve ZLT (Zero Lag Trend) ile trendin yönü ve gücü ölçülür.

### 3. Dinamik Exit Stratejisi 🚪
* **Funding Limit Exit:** Eğer fonlama oranları "aşırı" seviyeye (Örn: %0.03 üzeri) çıkarsa, teknik hedef gelmese bile Jarvis "Piyasa çok kalabalıklaştı" diyerek erken çıkış (Early Exit) sinyali üretir.
* **Volatility Trail:** Volatilite arttıkça stop seviyesini dinamik olarak sıkılaştırır.

---

## 📊 Ekran Görüntüleri

### 1. "Fisherman" Dashboard
> *Sağ alttaki panelde Binance, OKX ve Bybit borsalarının fonlama oranlarını ve Open Interest (OI) değişimini anlık izleyen veri merkezi.*
`![Fisherman Dashboard](buraya_dashboard_resmi.png)`

### 2. Sniper Giriş ve R:R Hesabı
> *Jarvis'in "Strong Buy" sinyali ürettiği an. Otomatik hesaplanan Risk:Reward oranı ve likidite havuzlarına (Liquidity Pools) konulan hedefler.*
`![Jarvis Signal](buraya_sinyal_resmi.png)`

### 3. Tuzağı Tespit Etme (Trap Detection)
> *Fiyat yükselirken Funding Rate'in aşırı ısınması sonucu Jarvis'in alım yapmayıp (veya satış verip) düşüşten koruduğu bir örnek.*
`![Trap Detection](buraya_tuzak_resmi.png)`

---

## ⚙️ Teknik Detaylar

* **Piyasa:** Bitcoin (BTC/USDT) & Major Altcoinler
* **Veri Kaynakları:** Binance, OKX, Bybit, TradingView CryptoCap
* **Kullanılan Konseptler:** Weighted Average Funding, Open Interest Delta, SMC (Order Blocks, BOS/CHoCH)
* **Zaman Dilimi:** Scalping (15dk-1S) ve Swing (4S-Günlük)

## ⚠️ Yasal Uyarı

Bu kodlar ve stratejiler tamamen eğitim ve AR-GE amaçlıdır. Kripto para piyasaları ve türev işlemler (Vadeli İşlemler) yüksek risk içerir. **Yatırım Tavsiyesi Değildir (NFA).**
