# 🛣️ MarketRadar Yol Haritası (Roadmap)

Bu roadmap, MarketRadar projesinin MVP geliştirme sürecini fazlara ve sprintlere ayırarak planlamaktadır.

---

## 🎯 Genel Fazlar

| Faz   | Hedef                                       | Süre    |
| ----- | ------------------------------------------- | ------- |
| FAZ 0 | Kurulum ve iskelet çıkarımı                 | 2 gün   |
| FAZ 1 | Veri toplama ve parsing sistemi             | 1 hafta |
| FAZ 2 | LLM entegrasyonu ve içerik yorumlama        | 1 hafta |
| FAZ 3 | Bildirim + Dashboard                        | 1 hafta |
| FAZ 4 | Geri bildirim sistemi + ilk kullanıcı testi | 1 hafta |

---

## 🧱 FAZ 0 – Proje İskeleti ve Hazırlık

**Amaç:** Kod yapısı, klasörler, veri modelleri, örnek datalar hazır olsun.

- [ ] Proje klasör yapısı oluştur (.NET, Python ayrımı)
- [ ] SEC ve haber API credential'ları alınsın
- [ ] Veri modelleri (`Document`, `NewsItem`, `Insight`) tanımlansın
- [ ] Örnek belge ve haber JSON’ları indirilsin
- [ ] GitHub repo oluştur + README yazılsın

---

## 📥 FAZ 1 – Veri Toplama Katmanı

**Amaç:** Her gün otomatik veri çekip saklamak.

- [ ] SEC Edgar’dan 8-K belgelerini çek (CIK bazlı veya rastgele)
- [ ] NewsAPI üzerinden sektör bazlı haberleri al
- [ ] Verileri normalize edip PostgreSQL’e kaydet
- [ ] Veri erişimi için servis yaz (.NET API)

---

## 🤖 FAZ 2 – LLM ile Yorumlama

**Amaç:** Ham belge ve haberleri GPT ile özetletip skorlamak

- [ ] Belge özeti çıkarma prompt'u tasarla
- [ ] Yatırımcıya etkisi çıkaran prompt tasarla
- [ ] Özet + etki + önem skoru üret (1–10)
- [ ] Sonuçları `Insights` tablosuna yaz

---

## 📢 FAZ 3 – Bildirim ve Dashboard

**Amaç:** Sonuçları kullanıcıya göstermek ve bildirmek

- [ ] Telegram Bot ile günün özetini gönder
- [ ] Basit bir React/Blazor dashboard hazırla (latest insights)
- [ ] Kullanıcı bazlı filtreleme (gerekirse sabit ayarlar)

---

## 🔄 FAZ 4 – Kullanıcı Testi + Geri Bildirim

**Amaç:** İlk kullanıcılarla test edip sistemin refleksini görmek

- [ ] MVP’yi 3 yatırımcıyla test et
- [ ] “Bu önemliydi / değildi” feedback butonu ekle
- [ ] Geri bildirim skorlarını sistemde sakla
- [ ] MVP sonrası pivot noktaları belirle

---

## 🔚 Sonuç

Bu roadmap, MVP sürecini 3-4 haftalık bir periyotta, ölçülebilir hedeflerle ilerletmek için yapılandırılmıştır.  
Yol boyunca her sprint sonunda:
- Hedeflerin üzerinden geçilecek,
- Neler çalışıyor, ne eksik gözden geçirilecek.

> “Plan sabittir” değil, “plan öğrenmeye izin verir” felsefesiyle yürürüz.
