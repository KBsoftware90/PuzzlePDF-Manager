# PuzzlePDF

PuzzlePDF’nin Windows ve Linux kurulumları ile uygulama içi güncelleme dosyaları
bu depodaki **Releases** bölümünde dağıtılır. Kaynak kod bu depoda yer almaz.

**İlk kurulum paketleri hazırlanıyor.** Bir sürüm yayınlandığında indirme
bağlantıları [Sürümler](https://github.com/KBsoftware90/PuzzlePDF-Manager/releases)
bölümünde görünecek. Taslak sürümler herkese açık indirmeye sunulmaz.

## Kullanım planları

- **Başlangıç:** Birden fazla PDF’yi ayrı sekmelerde görüntüleme ve bütün temalar.
- **Pro:** Bunlara ek olarak çift ekran, PDF birleştirme, bölme, şifreleme ve PuzzlePDF Manager.

Satın alma ve hesap işlemleri PuzzlePDF web sitesi üzerinden yapılır.
GitHub’dan indirmek tek başına Pro lisansı vermez.

## Güncellemeler

Program, Ayarlar → Güncellemeler bölümünden yeni sürümü kontrol eder. Otomatik
indirme açıksa imzası ve dosya bütünlüğü doğrulanan paket kapanışta kurulabilir.
Kurulum için Qt Installer Framework tabanlı PuzzlePDF kurucusu kullanılmalıdır.
Eski `.deb` kurulumlarına bu yöntemle doğrudan yazılmaz.

Windows ve Linux paketleri aynı sürüm etiketinde (`vX.Y.Z`) bulunur.
Yayınlanan paketler yerinde değiştirilmez; yeni değişiklik yeni sürüm olarak çıkar.

- İmza doğrulama anahtarı: [update-public.pem](update-public.pem)
- Dağıtım düzeni: [RELEASING.md](RELEASING.md)

Özel imza anahtarları, hesap bilgileri, kullanıcı belgeleri ve PDF kasaları bu
depoya yüklenmez.
