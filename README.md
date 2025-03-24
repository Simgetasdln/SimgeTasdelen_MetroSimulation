# SimgeTasdelen_MetroSimulation
  Bu projede amaç, bir şehirdeki metro ağlarının üzerinde bulunan istasyonların arasındaki en az aktarmalı ve en hızlı rotaları bulmaktır. Bunun için BFS ve A* isimli iki algoritma kullanılır.
## Kullanılan Teknolojiler ve Kütüphaneler
  bu proje python diliyle yazılmıştır.
- collections: Bu kütüphane, deque (çift yönlü kuyruk) ve defaultdict gibi veri yapıları sağlamak için kullanılmıştır.
- deque: Kuyruk (queue) verisi için kullanılan, verilerin başına ve sonuna hızlıca eleman ekleyebilen bir veri yapısıdır. BFS algoritmasında rota takip etmek için kullanılır.
- defaultdict: Dict'in türevidir. Eğer anahtar bulunmazsa varsayılan bir değer döndürür. Bu projede Istasyon ve Hat verilerini tutmak için kullanılır.
- heapq: Bu kütüphane, A* algoritmasında öncelikli kuyruk yapısı oluşturmak için kullanılır. Küçükten büyüğe sıralanmış bir yığın yapısına dayalı olarak çalışır ve her defasında en düşük maliyetli istasyonu seçer.
- typing: Python tip ipuçlarını kullanmak için gereklidir. Dict, List, Set, Tuple, Optional gibi türler için kullanılmaktadır.

## Algoritmaların Çalışma Mantığı
- BFS Algoritması: BFS algoritması, bir ağda veya grafikte en kısa yolu bulmak için kullanılan temel algoritmalardan biridir. Algoritma, bir başlangıç noktasından tüm komşularını ziyaret eder ve her adımda bir sonraki komşulara geçer. Bu süreç, hedefe ulaşana kadar devam eder. 
- A* Algoritması: A* algoritması, hedefe en hızlı şekilde ulaşmak için kullanılan önemli bir algoritmadır. Öncelikli kuyruk kullanarak her adımda en düşük maliyetli rotayı seçer. Doğru ve hızlı sonuçlar verir.
- Neden Bu Algoritmaları Kullandık?
  BFS katmanlı yapısı sebebiyle en kısa yolu basit ve etkili bir şekilde hesaplar.
  A* ise hedefe en hızlı yolu bulmak için kullanılan güçlü bir algoritmadır. BFS algoritmasından farklı olarak, sadece bulunduğumuz noktadan hedefe olan mesafeyi dikkate almaz, aynı zamanda o noktaya ulaşmak için harcanan toplam zamanı da göz önünde bulundurur.sadece gerekli istasyonları ziyaret eder bu nedenle hızlı ve verimlidir.
  Bu iki algoritmanın bir arada kullanılması, kullanıcılara hem minimum aktarma sayısını hem de en hızlı rotayı sunar.
  
## Örnek Kullanım ve Test Sonuçları
kod çalıştırıldığında alınan sonuç aşağıda verilmiştir:

=== Test Senaryoları ===

1. AŞTİ'den OSB'ye:
En az aktarmalı rota: AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB
En hızlı rota (25 dakika): AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB

2. Batıkent'ten Keçiören'e:
En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
En hızlı rota (21 dakika): Batıkent -> Demetevler -> Gar -> Keçiören

3. Keçiören'den AŞTİ'ye:
En az aktarmalı rota: Keçiören -> Gar -> Gar -> Sıhhiye -> Kızılay -> AŞTİ
En hızlı rota (19 dakika): Keçiören -> Gar -> Gar -> Sıhhiye -> Kızılay -> AŞTİ


## Projeyi Geliştirme Fikirleri
- Farklı Ulaşım Modlarıyla Entegre Edilebilir: Metro hatları dışında otobüs, tramvay gibi farklı ulaşım modları da eklenebilir. Böylece, çoklu ulaşım yöntemleriyle birleşik rotalar önerilebilir.
- Kullanıcı Tercihleri Dahil Edilebilir: Kullanıcıların rahatlık veya yürüyüş mesafesi gibi tercihlerine göre en uygun rotayı öneren bir sistem geliştirilebilir. Örneğin, kullanıcılar yürüyüş mesafesi kısa olan istasyonları tercih edebilirler.
- Gerçek Zamanlı Verilerle Entegrasyon: Gerçek zamanlı metro durak durumu ve ulaşım verileri ile entegrasyon yapılabilir. Böylece, istasyonlarlardaki yoğunluk veya geçici kapanmalar gibi faktörler ile rota hesaplamaları daha dinamik hale getirilebilir.
