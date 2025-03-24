# Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu) 

Bir metro ağı içindeki istasyonlar arasında en az aktarma yapan veya en hızlı rotayı bulan bir sistemin oluşturulması hedeflenmiştir. Projede kullanılan algoritmalar ve örnek kullanım senaryoları aşağıda detaylandırılmıştır.

## Özellikler

- **İstasyon ve Hat Yönetimi:** İstasyon ekleme, hat ekleme ve istasyonları hatlara bağlama işlevleri.
- **En Az Aktarmalı Rota Bulma:** Başlangıç ve bitiş istasyonları arasında en az aktarma ile rota bulma.
- **En Hızlı Rota Bulma:** Başlangıç ve bitiş istasyonları arasında en kısa sürede rota bulma.
- **BFS Algoritması** En hızlı rotayı bulmak için kullanılmıştır.
- **AYıldız Algoritması:** En hızlı rota bulma için A* arama algoritması kullanılmıştır.
- **Basit Heuristik:** A* algoritması için heuristik fonksiyonu kullanılmıştır.

## Kullanılan Algoritmalar
### 1. Genişlik Öncelikli Arama (BFS - Breadth-First Search)
En az aktarma yapan rotayı bulmak için BFS algoritması kullanılmıştır. BFS, başlangıç istasyonundan itibaren tüm komşu istasyonları sırayla gezerek hedef istasyona ulaşan en kısa yolu bulur.
#### Adımlar:
- Başlangıç istasyonu bir kuyruğa eklenir.
- Kuyruğun başındaki istasyon işlenir ve ziyaret edildiği işaretlenir.
- Komşu istasyonlar kuyruğa eklenir (eğer daha önce ziyaret edilmediyse).
- Hedef istasyona ulaşıldığında, o ana kadar geçen yol kaydedilir.
- En az aktarmalı rota döndürülür.

### 2. A* Algoritması
En hızlı rotayı bulmak için A* algoritması kullanılmıştır. A*, bir istasyondan hedef istasyona giderken tahmini maliyet (heuristic) ve gerçek maliyet arasında bir denge kurarak en kısa sürede ulaşılacak rotayı bulur.
#### Adımlar:
- Başlangıç istasyonu bir öncelikli kuyruğa eklenir.
- Kuyruğun en düşük maliyetli elemanı seçilir ve işlenir.
- Komşu istasyonlar hesaplanır ve kuyrukta güncellenir.
- Hedef istasyona ulaşıldığında en hızlı rota ve geçen süre döndürülür.

## Kullanım
örnek metro istasyonları ve bağlantılar tanımlanmıştır. Aşağıdaki fonksiyonları çağırarak belirli istasyonlar arasındaki en iyi rotayı bulabilirsiniz:
- rota = metro.en_az_aktarma_bul("M1", "K4")  # AŞTİ'den OSB'ye en az aktarma
- rota, sure = metro.en_hizli_rota_bul("M1", "K4")  # AŞTİ'den OSB'ye en hızlı rota

## Kurulum

1.  Proje dosyalarını GitHub'dan klonlayın veya indirin.
2.  `RemziEmreKahveci_metro_agi.py` dosyasını çalıştırın.
3.  Örnek kullanım senaryolarını inceleyerek kendi başlangıç ve bitiş istasyonlarınızı girin.

## Gereksinimler
-   Python 3
  
## Proje Yapısı
-   `RemziEmreKahveci_metro_agi.py`: Metro ağ haritası ve rota bulma uygulamasının kaynak kodu.
-   `README.md`: Proje hakkında bilgi veren dosya.
