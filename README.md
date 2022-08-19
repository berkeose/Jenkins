# Jenkins
## DevOps Nedir?
### Dev&Ops ekibini kültür,uygulama ve araçlar düzeyinde birleştirme felsefesidir.

## Continous Integration (Sürekli Entegrasyon)
### Sürekli entegrasyon, geliştiricilerin yazdıkları yeni kodu kod tabanına günde en az bir kez ekleyerek geliştirme döngüsü boyunca daha sık entegre ettiği bir yazılım geliştirme sürecidir. Entegrasyon sorunlarını, düzeltmenin daha kolay olduğu daha erken dönemde belirlemek için derlemenin her yinelemesinde otomatikleştirilmiş test gerçekleştirilir. Bu, yayın için gerçekleştirilen son birleştirmede de sorunların önlenmesine yardımcı olur. Genel olarak sürekli entegrasyon, derleme sürecinin kolaylaştırılmasına yardımcı olur; bu da yazılım kalitesinin daha yüksek, teslimat zamanlamalarının daha öngörülebilir olmasını sağlar.

## Continous Delivery (Sürekli Teslim)
### Sürekli teslim, ekiplerin kısa döngüler halinde yazılım ürettiği, yazılımın herhangi bir zamanda ve yazılımı serbest bırakırken manuel olarak yapmadan güvenilir bir şekilde yayınlanabilmesini sağlayan bir yazılım mühendisliği yaklaşımıdır.

## Jenkins Nedir?
### Jenkins basit tanım ile, bir yazılım projesinde dinamik olarak gerekli olan yapısal işlemleri otomatize ederek projeyi hızlı, kolaylıkla hata raporlaması ve kolay test edilip hataların fixlenebilmesini sağlayan bir CI(Continous Integration) aracıdır.

### Kısacası Jenkins ‘Bu işlemlerle vakit kaybetmek istemiyorum, projemi kendi repona çek, oradaki istediğim test işlemlerini yap, ayağa kaldır, sonra deploy et. Bu işlemlerde fail eden bir durum olursa beni notification ile bilgilendir. Belirli aralıklarla github’ı da yokla. Bu yoklamalarda sana emrettiğim işlemleri tekrar et.’ gibi isteklerimizi yerine getiriyor. Bu noktada tüm bu işlemleri manuel olarak yaptığımız taktirde hem zaman hem hata riski hem de iş gücü sarfetmiş oluyoruz. Jenkins tüm süreçleri dikkatli ve müthiş bir şekilde basitleştirip otomatikleştiriyor.

## İlk Jenkins Job'u
### İlk olarak bir job yaratmak için bir Job ismi belirtip nasıl yapılandıracağımızı seçiyoruz.
![1](https://user-images.githubusercontent.com/81867200/185698209-2a3b7742-bf35-4808-b705-e02707e11958.png)
### Job'un içine girdikten sonra Build Steps kısmına gelip Execute Shelli seçip içine shell'de çalıştırmak istediğimiz komutu girebiliriz.
![2](https://user-images.githubusercontent.com/81867200/185698967-b683a2f8-0afd-44bd-a547-d82c31579e50.png)
### Kaydettikten sonra Build Now' a tıklayıp consol outputumuzu kontrol edelim.
![3](https://user-images.githubusercontent.com/81867200/185699385-1c00b7d1-4f91-4f2e-8181-adcfb2dc02cd.png)
İlk job'umuzu yaratmış olduk.

### Bir başka Execute Shell örneği:
![4](https://user-images.githubusercontent.com/81867200/185700203-fe8cd1be-707a-4cf7-8f12-abf6cf2f8441.png)
Bu şekilde bir komut belirtirsek consol outputumuz şimdiki tarih ve saati gösterir.

### Execute Shell ile bir ortam değişkeni kullanarak nasıl işlem yapabiliriz onu görelim.
![5](https://user-images.githubusercontent.com/81867200/185701190-4d020f9f-8cda-4b4e-b77c-5899387a5d43.png)

### Job outputumuzu farkli bir adrese göndermek için aşağıdaki komut gibi yönlendirme işlemi yapabiliriz.
![6](https://user-images.githubusercontent.com/81867200/185702159-f90295e9-492b-4178-9f04-aae0944f9768.png)


## Parametre Kullanımı
### Parametreler kullanarak job yaratmak için Job Configuration'da "This project parameterized" seçeneiğini seçerek jobumuzu hangi parametre ile oluşturmak istediğimizi belirtip ona göre shell kısmında belirttiğimiz parametreleri kullanabiliriz.
![7](https://user-images.githubusercontent.com/81867200/185703927-1e926a3f-6ffe-48f1-8af5-67859e495763.png)
![8](https://user-images.githubusercontent.com/81867200/185703968-db08c60d-2d10-401c-a2dd-6d507c38d66d.png)
### Job'umuzu her build ettiğimizde parametreleri girmemiz gerekir.

## Jenkins Plugin Nedir?
### Jenkins kendi bünyesinde yüzlerce eklenti bulundurur, bu eklentilerin hangilerini kullanacağımız tamamen gereksinim duyduğunuz işleme göre değişiklik gösterir.
### Örneğin her build sonrası mail göndermek istersek bunun için Email Extension eklentisini, Build işleminde arayüzünden parametre göndermek istersek Extended Choice ### Parameter eklentisini indirip yüklememiz gerekir.

## Jenkins Plugin Nasıl Yüklenir?
### Manage Jenkins > Plugins >Available‘ a gelerek istenen pluginler yüklenir. Filter kısmından istenen plugin aranabilir.

## Hassas Bilgileri Jenkinste Nasıl Koruruz?
### Örneğin,eğer başka servislerden olan Key'lerimiz varsa bunu Jenkins'te Credentials altında Add Credetinals diyerek Credatinals Kind'ı belirtip bu keylerimizi koruyabiliriz.
[9](https://user-images.githubusercontent.com/81867200/185706529-d37ca265-87db-4253-ad50-5b7917960d3f.png)

## Jenkins ve Güvenlik
### Jenkins'te kullanıcıları ve ilgili izinlerini ayarlama olanağına sahipsiniz. Varsayılan olarak, herkesin Jenkins'te işleri veya diğer idari görevleri tanımlayabilmesini istemeyeceksiniz. Bu sebeple Jenkins, yerinde bir güvenlik yapılandırmasına sahiptir.

### Jenkins'te Güvenliği yapılandırmak için:
### Jenkins'i Yönet'e tıklayın ve 'Configre global security' seçeneğine tıklayın.
![10](https://user-images.githubusercontent.com/81867200/185708621-a17f5de9-b940-4cce-a01b-1359f9dff177.png)
### Güvenliği Etkinleştir seçeneğine tıklayın. Örnek olarak, Jenkins'in kendi kullanıcı veritabanını korumasını istediğimizi varsayalım, bu nedenle Güvenlik Alanında 'Jenkins'in kendi kullanıcı veritabanı' seçeneğini seçin.
![11](https://user-images.githubusercontent.com/81867200/185710674-fc42e9a1-b6a9-4d48-b7f1-180f02579748.png)
### Sisteme farklı kullanıcılar oluşturup ekleyebiliriz Jenkins'i Yönet'e gittiğinizde ve aşağı kaydırdığınızda, bir 'Kullanıcıları Yönet' seçeneğini görebilirsiniz. 
![12](https://user-images.githubusercontent.com/81867200/185710551-54832dda-3879-4864-baa2-12b257118ec6.png)
Yetkilendirleme işlemelrini yapabiliriz . Jenkins'i Yönet → Configure global security'a gidin.


