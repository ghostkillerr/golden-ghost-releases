# Golden Ghost Releases

Bu depo Golden Ghost oyununun oyunculara sunulan resmî dağıtım noktasıdır. Oyunun kaynak kodu ayrı ve gizli bir depoda tutulur; bu depoda yalnızca sürümlendirilmiş kurulum paketleri bulunur.

## Oyuncular için indirme

Ana oyun paketini [en güncel kod sürümünden](https://github.com/ghostkillerr/golden-ghost-releases/releases/latest) indirin. Kullanılacak dosya `golden_ghost.zip` dosyasıdır. GitHub'ın otomatik oluşturduğu “Source code” ZIP/TAR dosyaları oyun paketi değildir.

Oyunun güncelleyicisi gereken kod ve ses paketlerini otomatik indirir. Temiz kurulumda sesler yoksa en yeni `audio-vX.Y.Z` sürümündeki `audio_update.zip` ayrıca alınır.

## Yayın sözleşmesi

- Kod yayınları `vX.Y.Z`, ses yayınları `audio-vX.Y.Z` etiketi kullanır.
- Kod yayınında `golden_ghost.zip`, `golden_ghost.zip.sha256` ve `golden_ghost.manifest.json` birlikte bulunur.
- Ses yayınında `audio_update.zip`, `audio_update.zip.sha256` ve `audio_update.manifest.json` birlikte bulunur.
- `Latest` etiketi yalnızca kod yayınını gösterir; ses yayınları ana indirme bağlantısının yerini almaz.
- Manifest dosyası kaynak commit'i, paket sürümünü, boyutunu ve SHA-256 özetini kaydeder.
- Oyunun güncelleyicisi arşivi kurmadan önce yayımlanmış `.sha256` dosyasına göre doğrular.
- Depoda immutable releases etkindir; yeni bir sürüm yayımlandıktan sonra etiketi ve ekli dosyaları değiştirilemez.

Eksik ZIP, checksum veya manifest içeren bir yayın tamamlanmış kabul edilmez ve oyunculara duyurulmamalıdır.

## Elle SHA-256 doğrulama

Doğrulayacağınız ZIP dosyası ile ona ait `.sha256` dosyasını aynı Release sayfasındaki **Assets** bölümünden indirin. İki dosyanın aynı sürüme ait olduğundan emin olun.

Windows PowerShell ile indirilen paketin bulunduğu klasörde özetini görmek için:

```powershell
Get-FileHash -Algorithm SHA256 .\golden_ghost.zip
```

Çıktıdaki `Hash` sütununu `.sha256` dosyasında yazan SHA-256 özetiyle karşılaştırın; varsa dosya adını karşılaştırmaya dahil etmeyin. Büyük ve küçük harf farkı önemli değildir.

Çıktıyı aynı Release altındaki `golden_ghost.zip.sha256` değeriyle karşılaştırın. Ses paketi için aynı işlem `audio_update.zip` ve `audio_update.zip.sha256` ile yapılır.

## Güvenlik bildirimi

Şüpheli veya değiştirilmiş bir paket gördüğünüzde dosyayı çalıştırmayın. Ayrıntıları herkese açık issue içine hassas bilgi koymadan depo yöneticilerine iletin; mümkünse GitHub'ın özel güvenlik bildirimi kanalını kullanın.
