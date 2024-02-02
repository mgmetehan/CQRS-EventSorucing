# CQRS-EventSorucing
Acilis cumlesi CQRS icin
CQRS: Günümüz sistemleri bir önceki sistemlere nazaran artık daha fazla trafik almaktadır. Bu tür durumlarda uygulamaların erişilebilir olmasını, yüksek trafik altında da makul yanıt verme sürelerini elde etmeyi ve performanslı bir ürün ortaya çıkartmayı amaç edinmekteyiz.

Bu sunumda daha performanslı, ölçeklendirilebilir ve güvenli bir hale getirmemize yardımcı olan CQRS tasarım deseni hakkında bilgiler edineceğiz.

---
CQRS nedir
Cqrs nedir 2010 yilinda green yan tarafindan ortaya atiliyor

Yazilim gelistirme sureclerindeki karmasikligi azaltmanin ve daha iyi bir kod ogranizasyonunu saglamanin yollarini ararken CQS prensebinnden eninlenirerek ortaya cikar. Sistemleri daha esnek ve olceklenebilir hale getiriyor

---

CQS Nedir
- CQS’in ana fikrinden bahsetmek gerekirse; bir metot objenin durumunu değiştirmelidir ya da geriye bir sonuç dönmelidir, ancak 2 işlemi birden yapmamalıdır.
- 1988 yılında ortaya atılmıştır.

---

## CQRS'nin avantajları:

1. **Çeşitli Çözümler Sunma Esnekliği:**
    - CQRS, farklı ihtiyaçlara sahip uygulamalara özgü çözümler sunma esnekliği sağlar. Okuma ve yazma işlemlerini birbirinden ayırarak, her biri için en uygun teknoloji ve yaklaşımı seçme özgürlüğü verir. Örneğin, yazma kısmını Java, okuma kısmını Go ile implemente etmek mümkündür.

2. **Hata ve Kesinti İzolasyonu:**
    - Bir tarafta oluşan hata veya kesinti, diğer tarafı etkilemez. Bu, sistemin bir kısmında yaşanan sorunların diğer kısmı etkilemeyeceği anlamına gelir, bu da daha yüksek sistem güvenilirliği sağlar.

3. **Daha İyi Güvenlik Kontrolü:**
    - Komut tarafında yapılan işlemler, daha güvenli bir şekilde kontrol edilebilir ve yetkilendirilebilir.

4. **Read Model Optimizasyonu:**
    - Sorgu tarafında kullanılan "Read Model" veritabanları, özellikle sorgular için optimize edilebilir, bu da daha hızlı sorgu yanıtları sağlar.

5. **Farklı Domain Logic Üzerinde Çalışma:**
    - CQRS, her bir ekibin farklı domain mantığı üzerinde çalışabileceği bir yapı oluşturabilir. Okuma ve yazma modellerini ayırmak, farklı ekiplerin kendi iş mantıklarını daha iyi yönetmelerini sağlar.

6. **Bakım Kolaylığı:**
    - Sistemin bakımı daha kolaydır çünkü komut ve sorgu işlemleri ayrı ayrı ele alınır. Bir kısmın değiştirilmesi diğerini etkilemez.

7. **Geliştirme Hızı:**
    - Geliştirme sürecini hızlandırabilir çünkü komut ve sorgular farklı ekipler veya modüller tarafından eşzamanlı olarak geliştirilebilir.

8. **Bekleme Süresi Olmadan İşlemlerin Yürütülmesi:**
    - Okuma ve yazma işlemlerini ayırarak, okuma işlemlerinin yazma işlemleri nedeniyle bekletilmesi gerekmez. Her iki taraftaki işlemler bağımsız olarak yürütülür.

9. **Bağımsız Ölçekleme:**
    - CQRS, okuma ve yazma işlemlerini birbirinden bağımsız olarak ölçeklendirme imkanı sunar. Bu, sistemdeki yük artışlarına daha etkili bir şekilde yanıt verilmesini sağlar.
        - **Ölçeklenebilirlik**; bir sistem, uygulama veya işletme mimarisinin, artan yük veya talep durumunda kaynakları daha verimli bir şekilde kullanabilme ve işlemleri başarıyla sürdürebilme yeteneğini ifade eder.

---

## CQRS dezavantajları:

1. **Karmaşıklık ve Öğrenme Eğrisi:**
   - CQRS, geleneksel monolitik mimarilere göre daha karmaşık bir yapı sunar. Bu da ekibin CQRS konseptini anlaması ve uygulaması için daha fazla çaba harcamasına neden olabilir.

2. **Artan Geliştirme Zamanı:**
   - CQRS'yi uygulamak ve sürdürmek, geleneksel bir yapıya kıyasla daha fazla geliştirme zamanı ve çaba gerektirebilir. Özellikle küçük projelerde bu ekstra karmaşıklık ve maliyet anlamsız olabilir.

3. **Veri Senkronizasyonu Zorlukları:**
   - Okuma ve yazma modellerinin ayrılması, veri senkronizasyonunu yönetmeyi zorlaştırabilir. İki model arasındaki veri tutarsızlıklarıyla başa çıkmak, dikkatli planlama ve uygulama gerektirebilir.

4. **İki Veritabanı Kullanımı & Maliyet Artışı:**
   - CQRS genellikle iki farklı veritabanı modelini içerir: biri komutlar için, diğeri sorgular için. İki farklı veritabanı türünü yönetmek, bakımını yapmak ve senkronize etmek ek bir karmaşıklık getirebilir.

5. **Eğitim ve Adaptasyon Zorlukları:**
   - CQRS'nin getirdiği farklı düşünce ve tasarım paradigması, ekibin alışkın olduğu geleneksel yöntemlerden farklıdır. Bu nedenle, ekibin eğitilmesi ve yeni yaklaşıma uyum sağlaması zaman alabilir.

6. **İş Süreçleri Arasındaki Kopukluk:**
   - CQRS, okuma ve yazma işlemlerini tamamen ayırdığı için, iş süreçleri arasında bir miktar kopukluk olabilir. Bu, geliştiricilerin ve iş analistlerin sistem genelinde tam bir görünürlük sağlama konusunda dikkatli olmalarını gerektirebilir.

7. **Artan İletişim İhtiyacı:**
   - CQRS, komut ve sorguları ayırarak farklı modellerde çalıştığı için, bu iki taraf arasında etkileşim ve iletişim ihtiyacını artırabilir.

Her proje ve uygulama farklıdır, bu nedenle CQRS kullanımının avantajları ve dezavantajları, projenin ihtiyaçlarına ve gereksinimlerine bağlı olarak değerlendirilmelidir.

----

## CQRS'i Ne Zaman Kullanmalıyım ve Kullanmamalıyım?

---

## CQRS Ne Zaman Kullanılmalı ?

1. **Karmaşık İş Mantığı:**
   - Projede iş mantığı oldukça karmaşık ve birçok farklı iş akışını içeriyorsa, CQRS kullanmak bu karmaşıklığı daha iyi yönetmenize yardımcı olabilir.

2. **Farklı İhtiyaçlara Sahip Modeller:**
   - Okuma işlemleri genellikle farklı ihtiyaçlara sahiptir ve sık sık optimize edilmiş veri modelleri kullanılır. Yazma işlemleri ise daha karmaşık olabilir. Bu durumda CQRS, her bir ihtiyaca uygun modellerin kullanılmasına izin verir.

3. **Yüksek Trafikli Sistemler:**
   - Yüksek trafikli sistemlerde, okuma ve yazma işlemlerini ayırarak ölçeklenebilirlik avantajlarından faydalanabilirsiniz. Bu, sistem performansını artırabilir.

4. **Farklı Veritabanı ve Teknoloji Kullanımı:**
   - Farklı okuma ve yazma modelleri için farklı veritabanları veya teknolojiler kullanmak istiyorsanız, CQRS bu çeşitliliği yönetmek için uygundur.

5. **Bağımsız Geliştirme ve Dağıtım:**
   - Ekiplerin okuma ve yazma işlemleri üzerinde bağımsız olarak çalışmalarını ve değişiklikleri daha hızlı dağıtmalarını istiyorsanız, CQRS bu esnekliği sunabilir.

6. **Hata ve Kesinti İzolasyonu || Uygulama Güvenilirliği :**
   - Okuma ve yazma işlemlerini ayrı tutarak, bir tarafta oluşan hataların diğerini etkilememesi önemliyse, CQRS kullanmak sistemin güvenilirliğini artırabilir.

7. **Event Sourcing Kullanımı:**
   - Event Sourcing gibi özellikleri projenizde kullanmayı düşünüyorsanız, CQRS bu yapıyı destekleyen bir mimari sağlar.

---

## CQRS’i Ne Zaman Kullanmamalıyız?

1. **Proje Karmaşıklığı ve Ölçeği Küçükse:**
   - Küçük ölçekli ve karmaşıklığı düşük projelerde CQRS kullanmak, gerekli olmayan karmaşıklığı ekleyebilir. Basit CRUD (Create, Read, Update, Delete) işlemleri için CQRS kullanmak, projenin gereksinimlerini aşabilir.

2. **Ekip Deneyimi ve Eğitimi Yetersizse:**
   - Ekip CQRS konseptine yeterince aşina değilse veya deneyimi yoksa, bu mimariyi uygulamak sorunlara neden olabilir. CQRS, ekip üyelerinin eğitimi ve uyumu gerektirebilir.

3. **Ekstra Karmaşıklık İstenmiyorsa:**
   - Projenin gereksinimleri, okuma ve yazma işlemlerini ayrı tutmaya veya farklı veritabanları/teknolojileri kullanmaya ihtiyaç duymuyorsa, CQRS kullanmak gereksiz bir karmaşıklık getirebilir.

4. **Maliyet ve Kaynak Sınırlamaları:**
   - CQRS, iki farklı veritabanı kullanımını içerebilir, bu da ek maliyet ve kaynak kullanımına neden olabilir. Proje bütçesi ve kaynakları sınırlıysa, CQRS kullanımı değerlendirilmelidir.

5. **Hızlı Geliştirme ve Prototip İhtiyacı:**
   - Hızlı bir şekilde geliştirme yapılması veya prototip oluşturulması gerekiyorsa, CQRS kullanmak ekstra karmaşıklık ve zaman gerektirebilir. Bu durumda basit bir mimari tercih edilebilir.

6. **Veri Tutarlılığı Mutlak Öncelik Değilse:**
   - Bazı uygulamalarda veri tutarlılığı mutlak bir öncelik olmayabilir. Eğer bu durum geçerliyse, CQRS kullanmak gereksiz bir karmaşıklık yaratabilir.

7. **Event Sourcing Gereksinimi Yoksa:**
   - Eğer projede Event Sourcing gibi özellikler gerekmiyorsa, CQRS kullanımı düşünülmelidir. Event Sourcing, ekstra karmaşıklık getirebilir ve gereksinimlere uygun olmayabilir.

8. **Performans Kritik Değilse:**
   - Performans, proje için kritik bir faktör değilse ve basit CRUD operasyonları yeterliyse, CQRS kullanımı gereksiz olabilir.


---

## CQRS'in Kullanılabileceği Senaryolar

1. **Netflix:**
   - Netflix, büyük bir müşteri tabanına ve karmaşık bir içerik yönetim sistemine sahip. Kullanıcıların içeriklere erişimi okuma modeli üzerinden sağlanırken, içerik eklemek, kaldırmak veya öneri algoritmalarını güncellemek gibi komut işlemleri yazma modeli üzerinden gerçekleştirilebilir.

2. **E-Ticaret Platformları:**
   - E-ticaret platformu olarak yüksek veri trafiğiyle karşılaşan bir projedir. Ürün sorguları ve fiyat kontrolleri okuma modeli üzerinden yapılırken, sipariş oluşturma, envanter güncelleme gibi işlemler yazma modeli üzerinden yönetilebilir.

3. **Uber:**
   - Uber, kullanıcıların araçlarına erişimini ve sürüş verilerini okuma modeli üzerinden sağlar. Ancak yeni sürücü eklemek, sürücü konumunu güncellemek gibi işlemler yazma modeli üzerinden gerçekleştirilir.

4. **Twitter:**
   - Twitter, milyonlarca kullanıcı tarafından yapılan tweet sorgularını okuma modeli kullanarak gerçekleştirirken, yeni tweetlerin eklenmesi veya kullanıcı bilgilerinin güncellenmesi gibi işlemler yazma modeli üzerinden yönetilebilir.


## Referanslar
- CQRS Documents — Greg Young
- Clarified CQRS — Udi Dahan
- CQRS — Martin Fowler
- CQS — Martin Fowler
- Implementing DDD — Vaughn Vernon
- Azure Cloud CQRS pattern
- Command and Query Responsibility Segregation (CQRS) pattern — Microsoft Docs
- Software Architect’s Handbook — Joseph Ingeno
- Event Sourcing — Martin Fowler
- Code with Shadman — CQRS
