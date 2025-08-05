# 🚀 Unity’ye Başlarken – Getting Started

Bu dosya Unity’ye uzun bir aradan sonra döndüğümde kendime "nereden başlıyorduk lan?" dememek için var.  
Hedef: temel kurulumlar, editor yapısı, temel mantık → hızlı hatırlama.

---

## 🛠️ Unity Hub ve Kurulum

- Unity’yi [https://unity.com/download](https://unity.com/download) adresinden indir.
- Unity Hub üzerinden versiyon kur → Genelde **LTS (Long Term Support)** sürümlerini tercih et.
  - Mesela: `2022.3.xf1 LTS` gibi.
- Proje oluştururken:
  - **3D** ya da **2D** template seç (neye göre çalışacaksan).
  - Mobil için çalışacaksan → `Android Build Support` kutusunu da yükle.

📌 **Not:** Proje yolunu `C:/Users/KullanıcıAdı/Documents/UnityProjects` gibi bir yere verirsen derli toplu olur.

---

## 🧱 Unity Editor Yapısı – Arayüz Tanıtımı

### 🔹 Hierarchy (Hiyerarşi)
- Sahnedeki tüm nesneleri gösterir (kameralar, zemin, player, vs.).
- Obje ekleyeceksen → sağ tıkla → 3D Object / UI vs. seç.

### 🔹 Inspector
- Seçili objeye ait bileşenleri (component) gösterir.
- Position, Rotation, Rigidbody, Collider, Script... hepsi burada ayarlanır.

### 🔹 Project Panel
- Tüm dosya yapın burada durur.
- `Assets` klasörü → her şeyin ana evi.
- Alt klasör önerisi:
Assets/
├── Scripts/
├── Materials/
├── Prefabs/
├── Scenes/
└── Sprites/


### 🔹 Scene & Game View
- `Scene`: objeleri yerleştirdiğin ve düzenlediğin alan.
- `Game`: oyunun oyuncuya nasıl gözüktüğünü gösterir.

---

## 🧩 GameObject ve Component Sistemi

Unity’de her şey bir `GameObject`’tir:  
- Kamera → GameObject  
- Oyuncu → GameObject  
- Düşman, UI butonu, zemin... hepsi.

Bunlara özellik (component) eklediğinde "akıllanırlar":
- Rigidbody: fizik kuralları gelir
- Collider: çarpışma algılar
- Script: kendi davranışını yazarsın

📌 **Not:** Kendi script’lerin de birer component’tir. Attach etmen gerekir!

---

## 🎮 Yeni Proje Oluşturduktan Sonra İlk Adımlarım

✅ `Scenes` klasörü oluştur, ana sahneyi içine kaydet (örn: `Main.unity`)  
✅ `Scripts`, `Prefabs`, `Materials`, `Audio`, `UI` gibi klasör yapını kur  
✅ Projeyi ilk açınca şu ayarları kontrol et:
- **Edit > Project Settings > Input Manager** (Eski sistem mi, yeni sistem mi?)
- **File > Build Settings** → Platform seçili mi?
- **Player Settings > Resolution & Presentation** (fullscreen, vs.)

---

## 📢 İpuçları / Hatırlatmalar

- 🎯 **Ctrl + S**: Sık sık kaydet. Unity bazen sahne kaydını otomatik yapmaz.
- 💥 Script yazınca Unity’ye geri dön, compile etmesini bekle.
- 🎮 Sahnede objeye script atayıp **public değişkenlere** değer vermeyi unutma.
- 🔁 Script'teki hatayı çözmeden Unity sahneyi çalıştırmaz.
- 📦 Script’i attığın obje sahnede değilse, çalışmaz.

---

## 🧠 Sık Sorulanlar (kendime)

> ❓ "Objem neden hareket etmiyor?"  
✔ Rigidbody ekli mi? `transform.position` mi `rb.MovePosition` mı kullanıyorsun?

> ❓ "Script yazdım ama görünmüyor?"  
✔ Class adı ve dosya adı birebir aynı mı?

> ❓ "Input algılanmıyor?"  
✔ Input System aktif mi? Doğru tuş ismi mi yazdın?

> ❓ "Obje çarpmıyor?"  
✔ Collider var mı? Rigidbody var mı? Biri `isTrigger` mı?

---

## ✅ Kurulumdan Sonraki Plan
1. `PlayerMovement.cs` yazılır
2. Kamera takip ayarlanır
3. UI yerleştirilir
4. Sahne kaydedilir
5. Build ayarları yapılır

---

🧾 Bu dosya sadece “nereye tıklıyorduk lan” dememek için oluşturuldu.  
Zamanla yeni notlar, hatırlatmalar, güncellemelerle büyütülecek.  


