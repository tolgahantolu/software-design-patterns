# Her Geliştiricinin Bilmesi Gereken Yazılım Tasarım Desenleri
Selam arkadaşlar, bu yazımda sizlere önemli yazılım tasarım desenlerinden (software design patterns) bahsedeceğim. İlk olarak kısaca yazılım tasarım desenleri nedir kısa bir giriş yapalım.

Yazılım tasarım desenleri, yazılım geliştirme sürecinde tekrar eden sorunları çözmek ve daha etkili, okunabilir, bakımı kolay, yeniden kullanılabilir bir kod tabanı oluşturmak için kullanılan yapılardır. Bu desenler, yılların deneyimiyle geliştirilmiş çözümleri içerir ve yazılım mühendisleri arasında ortak bir anlayış oluşturur. Yazılım tasarım desenleri, kodun sürdürülebilirliğini ve ölçeklenebilirliğini artırırken zaman kazandırır ve hataları azaltır.

## Önemli Yazılım Tasarım Desenleri
Birçok farklı yazılım tasarım deseni olsada biz burada önemli olanlarını göreceğiz.

### Singleton Design Pattern
Singleton Design Pattern, yaratıcı (creational) tasarım desenlerinden biridir. Yazılım geliştirme sürecinde, bazen yalnızca bir sınıftan bir nesne oluşturulmasını ve bu nesneye tüm uygulama boyunca erişilmesini isteyebiliriz. İşte bu noktada Singleton yazılım tasarım deseni devreye girer. Singleton deseni, bir sınıfın yalnızca bir nesnesinin olduğunu garanti etmek için kullanılır ve bu nesneye tüm istemcilerin erişmesini sağlar.

Singleton deseninin temel amacı, bir nesnenin yalnızca bir kez oluşturulmasını ve daha sonra bunun tüm istemciler tarafından kullanılmasını sağlamaktır. Bu, bellekte tek bir noktada tutulması ve veri tutarlılığının korunması anlamına gelir. Singleton deseni, paylaşılan bir kaynağa veya bir erişim noktasına sahip olmak istediğimiz durumlarda kullanışlıdır.

Singleton deseninin uygulanmasında, sınıfın yapısı ve davranışı özel olarak tasarlanmalıdır. Genellikle, sınıfın constructor'ı özel olarak tanımlanır ve private olarak işaretlenir, böylece dışarıdan doğrudan bir örnek oluşturulması engellenir. Singleton sınıfı içinde, sınıfın kendisine ait bir örneği tutan static bir değişken tanımlanır. Yalnızca bir kez oluşturulur ve daha sonra tüm istemciler tarafından erişilebilir hale gelir.

Singleton deseni, database bağlantısı, loglama, dosya işlemleri gibi birçok senaryoda kullanışlıdır. Ayrıca, çoklu kullanıcı senaryolarında, Singleton deseni thread güvenliği koruması sağlar.

Singleton deseninin yanlış kullanımı bazı ciddi sorunlara yol açabilir. Örneğin, çok fazla bağımlılık yaratabilir ve test edilebilirlik sorunlarına neden olabilir.

### Factory Method Design Pattern
Factory Method Design Pattern, yaratıcı (creational) tasarım desenlerinden biridir. Bu deseninin temel fikri, bir sınıfın nesne oluşturma sürecini alt sınıflara bırakarak esneklik sağlamaktır. Böylece, ilgili alt sınıfların nesneleri nasıl oluşturacaklarına karar vermesine olanak tanır ve yeni alt sınıflar eklemek veya var olanların davranışını değiştirmek kolaylaşır.

Genellikle, Factory Method deseninde bir üst sınıf veya arayüz tanımlanır ve bu üst sınıf veya arayüzü uygulayan alt sınıflar, kendi nesnelerini oluşturan Factory Method'u uygular. Bu Factory Method, genellikle statik bir metot olarak tanımlanır ve yeni bir nesne oluştururken alt sınıfın özel gereksinimlerini karşılayan nesneyi döndürür. Bu sayede, istemci, hangi alt sınıfın nesnesini oluşturduğunu bilmeksizin sadece Factory Method'u çağırarak nesne oluşturabilir.

Factory Method deseni, kodun genişletilebilirliğini artırır ve bağımlılıkları azaltır. Yeni bir alt sınıf eklemek istendiğinde, sadece Factory Method'u uygulayan yeni bir sınıf tanımlamak yeterlidir. Bu, kodun açık ve kapalı prensibine (Open-Closed Principle) uygunluğunu sağlar. Ayrıca bu desen, kodun daha temiz, sade ve daha az bağımlı olmasını sağlar.

Factory Method deseni, örneğin bir loglama mekanizması oluşturmak, veritabanı bağlantıları oluşturmak, örnekleme sürecini soyutlamak veya bir nesne havuzunu yönetmek gibi durumlarda kullanılabilir.

### Builder Design Pattern
Builder Design Pattern, yaratıcı (creational) tasarım desenlerinden biridir. Bu desen, karmaşık bir nesnenin adım adım oluşturulmasını sağlar ve nesnenin oluşturma sürecini temsil eden bir yapı oluşturur. Builder deseni, nesne oluşturma aşamalarını soyutlar, esneklik ve kontrol sağlar.

Builder deseni, bir nesnenin oluşturulma sürecini ayrıştırarak adım adım ilerler. Bu süreçte, bir Builder arayüzü veya soyut sınıfı tanımlanır ve bu arayüz veya soyut sınıfı uygulayan Concrete Builder sınıfları, nesne oluşturma işlemlerini gerçekleştirir. Ayrıca, bir Director sınıfı, oluşturma sürecini yönetir ve istemci kodun nasıl bir nesne oluşturacağını belirler.

Builder deseninde, istemci, Director sınıfını kullanarak bir Builder nesnesi oluşturur ve bu Builder nesnesini kullanarak nesnenin adım adım oluşturulma işlemlerini gerçekleştirir. Bu işlemler, Builder sınıfının metotları aracılığıyla gerçekleştirilir. Sonuç olarak, Builder deseni, istemcinin karmaşık bir nesneyi adım adım oluşturmasını sağlar ve nesne oluşturma sürecinin detaylarından istemciyi soyutlar.

Builder deseni, karmaşık nesnelerin oluşturulmasında ve farklı oluşturma senaryolarının yönetilmesinde kullanılır. Özellikle, nesnenin oluşturulma aşamaları ve parametreleri değişebilen durumlarda Builder deseni tercih edilir. Ayrıca, Builder deseni, nesne yapısının sadece bir kısmını oluşturmak veya alternatif yapılar oluşturmak için de kullanılabilir.

Bu desen, kodun okunabilirliğini ve bakımını artırır, nesne oluşturma sürecindeki adımları kontrol etmeyi sağlar ve istemcinin nesne yapısına ilişkin ayrıntılarla uğraşmasını engeller. Ayrıca, Builder deseni, tek bir Builder arayüzü veya soyut sınıfı üzerinden farklı nesne yapıları oluşturmayı sağlayarak tekrar kullanılabilirliği artırır.

### Prototype Design Pattern
Prototype Design Pattern, yaratıcı (creational) tasarım desenlerinden biridir. Bu desen, bir nesnenin oluşturulması maliyetli veya zaman alıcı olduğunda veya bir nesnenin farklı varyasyonlarını oluşturmak gerektiğinde kullanılır. Bu desenin ana fikri, bir prototip nesne oluşturmak daha sonra bu prototipten kopyalama yaparak yeni nesneler elde etmektir.

İstemci, bir prototip nesneye başvurarak yeni nesneleri oluşturabilir ve bunları ihtiyaçlarına göre yapılandırabilir. Bu şekilde, her bir nesne ayrı ayrı oluşturulmak yerine, mevcut bir prototipin kopyaları oluşturularak zaman ve kaynak tasarrufu sağlanır.

Prototip deseni, performans açısından avantajlıdır. Çünkü yeni nesne oluşturmak için maliyet gerektiren işlemler yerine, kopyalama işlemi daha hızlı ve daha verimli bir yöntemdir.

### Adapter Design Pattern
Adapter Design Pattern, yapısal (structural) tasarım desenlerinden biridir. Bu desen, bir nesnenin arabirimini başka bir nesneye uyarlamak için kullanılan bir tasarım desenidir. Bu desen, farklı arabirimlere sahip olan nesnelerin birlikte çalışmasını sağlamak için kullanılır. İki farklı sistem arasında uyumsuzlukk olduğunda veya mevcut bir sınıfın arabirimi başka bir sınıf tarafından kullanılması gerektiğinde Adapter Design Pattern devreye girer.

Adapter Design Pattern, adaptör sınıfı aracılığıyla bir sınıfın arabirimini hedeflenen arabirime dönüştürür. Bu sayede, müşteriler mevcut nesneye uygun olan arabirimi kullanabilirler. Adaptör sınıfı, hedeflenen arabirimde tanımlanmış olan metodları kendi içinde çağırarak uyum sağlar. Böylece, iki farklı nesne birlikte çalışabilir ve sistemdeki uyumsuzluk giderilebilir. Bu desen, sistemdeki esnekliği artırır ve mevcut kodun yeniden kullanılabilmesini sağlar.

Örneğin, bir uygulama mevcut bir veritabanı erişim katmanına sahip olabilir, ancak yeni bir veritabanı teknolojisi kullanmaya karar verildiğinde, tüm kodun bu yeni teknolojiyle uyumlu hale getirilmesi gerekebilir. Bu durumda, Adapter Design Pattern kullanılarak yeni veritabanı teknolojisiyle uyumlu bir adaptör sınıfı oluşturulabilir. Adaptör sınıfı, eski veritabanı erişim katmanıyla ilgili kodları yeni teknolojiye uygun hale getirir ve uygulamanın mevcut kodunu değiştirmeden yeni teknolojiyi kullanabilmesini sağlar.

### Chain of Responsibilty Design Pattern
Chain of Responsibility Design Pattern, davranışsal (behavioral) bir tasarım desenidir ve bir isteği yerne getiren nesnelerin bir zincir oluşturarak isteği zincir boyunca sırayla iletmelerini sağlar. Bu desen, isteği gönderen nesne ile işleyen nesneler arasındaki sıkı bağımlılığı azaltır ve isteğin hangi nesne tarafından işleneceğini dinamik olarak belirlemeyi sağlar.

Zincirin her bir halkası, isteği yerine getirme yeteneğine sahip bir nesneyi temsil eder. İsteği yerine getirmek için zincirin başından başlayarak ilerler ve uygun halkayı bulana kadar her bir halkadan geçer. Bir halka isteği yerine getirebilirse işler ve zincirin sonuna ulaşılır. Eğer halka isteği yerine getiremezse, isteği bir sonraki halkaya iletir.

Bu desenin avantajlarından biri, istek yerine getirme sürecinin esnekliğini artırmasıdır. Her bir halka, isteği farklı şekillerde yerine getirebilir veya tamamen direkt reddedebilir, böylece istek işleme davranışı kolayca değiştirilebilir. Ayrıca, zincir boyunca isteği iletmek için hiyerarşik bir yapı kullanıldığından, istek yerine getiren nesneler arasında çok da sıkı olmayan bağlantılar oluşturulur ve isteği yerine getiren nesnelerin değiştirilmesi veya eklenmesi kolaylaşır.

## Özet
Yazılım tasarım desenleri, yazılım geliştirme sürecinde sık karşılaşılan sorunlara yönelik çözüm önerileri sunan tekrarlanabilir tasarım kalıplarıdır. Bu kalıplar, kodun daha okunabilir, sürdürülebilir ve genişletilebilir olmasını sağlamak için kullanılır. Geliştiricilerin ortak bir anlayışa sahip olmalarını sağlar ve ekipler arasında işbirliğini artırır, daha da önemlisi verimli bir şekilde yazılım geliştirme sürecini yönetmeyi sağlar.

