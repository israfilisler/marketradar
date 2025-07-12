# 🧱 MarketRadar – Teknik Altyapı ve Teknoloji Yığını

Bu belge, MarketRadar projesinde kullanılacak teknolojileri, mimari yaklaşımı ve altyapısal tercihleri açıklamaktadır.  
Amaç, hem geliştiriciye hem de stratejik paydaşlara sistemin nasıl inşa edileceği konusunda şeffaflık sağlamaktır.

---

## 1. Amaç ve Yaklaşım

MarketRadar teknik altyapısı, hızlı MVP geliştirme, modüler yapı ve açık kaynak araçlarla entegrasyon üzerine kuruludur.  
Öncelikli hedefimiz; zaman kaybetmeden çalışan bir prototip ortaya koymak, sonrasında sistemi geri bildirimler doğrultusunda ölçeklemektir.

Yapı, gerektiğinde yatay büyümeye açık, gerektiğinde hafif servislerle taşınabilir olacak şekilde planlanmıştır.  
Yapay zekâ kullanımı dış servislerle (OpenAI vb.) entegre şekilde başlayacak, ancak uzun vadede kendi model pipeline'ımıza dönüşecektir.

---

## 2. Genel Mimari

Sistem üç ana katmandan oluşur:

1. **Veri Toplama Katmanı (Ingestion Layer)**  
   - SEC belgeleri, haber kaynakları ve sosyal medya API’lerinden veri çeker
   - Python tabanlı servisler kullanılır
   - Planlı olarak çalışan cron job’larla beslenir

2. **Yorumlama ve Zekâ Katmanı (LLM Layer)**  
   - OpenAI GPT-4o üzerinden içerik özetleme ve önem skoru üretimi yapılır  
   - Özel prompt mühendisliği ile yatırımcı odaklı içerik çıkarımı sağlanır

3. **Sunum ve Bildirim Katmanı (Presentation Layer)**  
   - Kullanıcıya bildirim gönderimi (Telegram, E-posta, Push)
   - Dashboard ile içerik gösterimi (React veya Blazor tabanlı)

Veri katmanları arası iletişim için RESTful API yapısı tercih edilmektedir.

---

## 3. Kullanılacak Teknolojiler

### 🧩 Backend

| Teknoloji                     | Amaç                                        |
| ----------------------------- | ------------------------------------------- |
| **.NET Core (C#)**            | API katmanı, iş akışı yönetimi              |
| **Python**                    | Veri toplama (SEC, haber), LLM entegrasyonu |
| **Flask/FastAPI (opsiyonel)** | Python tarafında hafif servisler            |

---

### 🖥️ Frontend

| Teknoloji                   | Amaç                                   |
| --------------------------- | -------------------------------------- |
| **Blazor** veya **React**   | Dashboard UI, kullanıcı içeriği sunumu |
| **TailwindCSS / Bootstrap** | Hızlı ve sade UI geliştirme            |

---

### 🔍 Veri Kaynakları

| Kaynak                             | Amaç                                |
| ---------------------------------- | ----------------------------------- |
| **SEC Edgar API**                  | 8-K, 10-Q belgeleri                 |
| **NewsAPI / JW Journey**           | Piyasa haberleri                    |
| **realtime-newsapi (open source)** | Anlık haber akışı için lokal stream |
| **RSS / Twitter (opsiyonel)**      | Alternatif haber kaynakları         |

---

### 🧠 Yapay Zekâ (LLM)

| Model                              | Kullanım                               |
| ---------------------------------- | -------------------------------------- |
| **OpenAI GPT-4o**                  | Özet çıkarma, yorum üretme, önem skoru |
| **Anthropic Claude 3 (opsiyonel)** | Alternatif LLM                         |
| **DeepSeek, Mistral (R&D)**        | Açık kaynak LLM testleri               |

---

### 🗄️ Veri Tabanı

| Teknoloji             | Amaç                                                     |
| --------------------- | -------------------------------------------------------- |
| **PostgreSQL**        | Belgeler, haberler, kullanıcı ayarları, insight skorları |
| **Redis (opsiyonel)** | Önbellek / geçici veri işlemleri                         |

---

### 📩 Bildirim Altyapısı

| Kanal                         | Amaç                         |
| ----------------------------- | ---------------------------- |
| **Telegram Bot**              | İlk sürümde hızlı bildirim   |
| **E-posta (SendGrid / SMTP)** | Özet gönderimi               |
| **Web push (ileride)**        | Gerçek zamanlı uyarı sistemi |

---

### ⚙️ DevOps & Çevre Yönetimi

| Araç                            | Amaç                                          |
| ------------------------------- | --------------------------------------------- |
| **Docker**                      | Servisleri bağımsız konteynerlerde çalıştırma |
| **GitHub Actions**              | CI/CD pipeline’ı (build, test, deploy)        |
| **Serilog / OpenTelemetry**     | Loglama ve monitoring                         |
| **VS Code + Jupyter + Postman** | Geliştirme ortamları                          |

---

## 4. Genişleme Planları (Opsiyonel)

- **Kendi LLM modelimizi eğitme (finansal belge corpus’uyla)**  
- **Mobil uygulama ve push notification**  
- **Kurumsal API (portföy yönetimi sistemlerine entegrasyon)**  
- **Kripto, tahvil ve emtia gibi yeni varlık sınıflarına açılma**

---

> Bu teknik yapı, hem bireysel yatırımcıya hizmet edecek esnekliği,  
> hem de gelecekte kurumsal pazarlara açılacak sağlamlığı birlikte sunar.
