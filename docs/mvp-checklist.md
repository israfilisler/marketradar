# ✅ MarketRadar – MVP Kontrol Listesi

Bu dosya, MVP geliştirmesine başlamadan önce tamamlanması gereken ön hazırlıkları içerir.  
Kodlamaya geçmeden önce teknik, işlevsel ve operasyonel olarak eksikler görülür.

---

## 1. Fonksiyonel Hedefler

| Hedef                                           | Durum |
| ----------------------------------------------- | ----- |
| SEC 8-K belgelerinin günlük olarak çekilmesi    | ⬜     |
| NewsAPI üzerinden haber akışı sağlanması        | ⬜     |
| Belgelerin LLM ile özetlenmesi                  | ⬜     |
| Haberlerin "önem skoru" ile değerlendirilmesi   | ⬜     |
| Tüm verilerin PostgreSQL'e yazılması            | ⬜     |
| Telegram bot ile günlük bildirim gönderimi      | ⬜     |
| Basit dashboard arayüzü (son haberler, özetler) | ⬜     |

---

## 2. Teknik Hazırlıklar

| Hazırlık                                               | Durum |
| ------------------------------------------------------ | ----- |
| .NET ve Python proje klasörleri oluşturuldu            | ⬜     |
| API anahtarları (SEC, NewsAPI, OpenAI) alındı          | ⬜     |
| Docker kurulumu ve `docker-compose.yml` hazır          | ⬜     |
| Prompt tasarımları oluşturuldu                         | ⬜     |
| Markdown belgeleri (roadmap, vision, stack) tamamlandı | ✅     |
| Test verileri hazırlandı (örnek 8-K, haber)            | ⬜     |

---

## 3. İlk Testler (Koddan Önce)

| Test                                        | Durum |
| ------------------------------------------- | ----- |
| SEC'den tek CIK ID ile belge çekiliyor mu?  | ⬜     |
| NewsAPI ile tek sektör başlığı alınıyor mu? | ⬜     |
| OpenAI'ye örnek prompt gönderiliyor mu?     | ⬜     |
| PostgreSQL'e basit `INSERT` test edildi mi? | ⬜     |
| Telegram bot'a mesaj atılabiliyor mu?       | ⬜     |

---

## 4. MVP Başlangıcı Hazır mı?

| Soru                                             | Cevap           |
| ------------------------------------------------ | --------------- |
| En az 2 örnek belge analiz edildi mi?            | ⬜               |
| Dashboard wireframe'i çizildi mi?                | ⬜               |
| İlk 3 haftalık sprint listesi hazır mı?          | ⬜               |
| Günlük veri akışı otomatik mi olacak, manuel mi? | 🟨 Geçici manuel |

---

> Bu liste tamamlandığında, MarketRadar MVP'sine **teorik olarak başlamak için tüm temel hazır** demektir.
