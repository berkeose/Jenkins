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


## Jenkins Global Envoriment Variables
### Jenkins'teki Ortam Değişkenleri nelerdir? Ortam değişkenleri, Jenkins'in bir projeye erişip enjekte edebileceği global anahtar/değer çiftleridir. Her proje için aynı değerleri kodlamaktan kaçınmak için Jenkins ortam değişkenlerini kullanın. Jenkins ortam değişkenlerini kullanmanın diğer faydaları arasında gelişmiş güvenlik bulunur.

https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#using-environment-variables

### Jenkins'i Yönet-> Configure System -> Global Properties altında enviroment-variables seçerek kendi ortam değişkenlerimizi de yaratabiliriz.

### Nasıl Job Otomatik Execute Edilir?

### Bir Job'umuzu her gün saat 1' de execute etmemiz lazim bunu nasil sağlarız? Configurations -> Build Triggers -> Periyodik olarak yapılandırı seçip aşağıdaki gibi bir girdi girersek bu Job artık otomatik olarak execute edilecektir. Eğer birden fazla Job'larımız varsa ve aynı saatte execute edilmesi gerekiyorsa bunun için sistem biraz yavaşlayacaktır. "H" kullanarak öncelik verilecek Job'u kendimiz ayarlayabiliriz.
![13](https://user-images.githubusercontent.com/81867200/185794240-12b85513-5017-463e-b044-8cf337463994.png)

## Jenkins&Mailer
### Jenkins'te mail yoluyla bildirim almak için Jenkins Mail Pluginini inidirmemiz gerekir.Sonra içinde olduğumuz Job'da"Post build actions" altında E-mail Notificationu seçip adresi girmemiz yeterli. Job Execute olduğunda başarılı veya başarısız olduğunu böylece bildirim olarak alabiliriz.


## Freestyle Jobs
### Yapıya adımlar ekleyerek GUI'yi kullanarak Jenkins'te Freestyle iş yapılandırırsınız. Freestyle işler size çok fazla esneklik sağlar. Ancak karmaşık sürekli teslim senaryolarını yapılandırmakta zorlanabilirsiniz.

## Pipeline Jobs
### Pipleline Jobs, kod kullanarak bir dizi talimat oluşturmanıza olanak tanır. Ayrıca farklı aşamaları tek bir yerde kolayca görselleştirebilirsiniz. En önemlisi, tüm kodu bir kod deposunda saklayabilirsiniz. Bu da, değişiklikleri sürümlendirmenize, denetlemenize ve izlemenize olanak tanır.
### Pipeline Jobs işleri Jenkinsfile kullanılarak oluşturulur. Ve Jenkinsfiles, komut dosyası dili olarak Apache Groovy'yi kullanır.

Pipeline
 Örnek: ![example-pipeline-in-classic-ui](https://user-images.githubusercontent.com/81867200/185795772-4e880a51-484a-4630-8be7-b7437d859ae3.png)



pipeline {
    agent none
    stages {
        
        stage("First") {
            agent {
                    docker { 
                        image 'ugurgungor/docker-with-sudo:latest'
                        args '-v /var/run/docker.sock:/var/run/docker.sock'
                    }
                }              
            
            steps {
                echo 'I am running in docker'
                sh 'docker ps'
            }
        }
    }
}

pipeline {
    agent none
    stages {
        
        stage("First") {
            agent {
                    docker { 
                        image 'ugurgungor/docker-with-sudo:latest'
                        args '-v /var/run/docker.sock:/var/run/docker.sock'
                    }
                }              
            
            steps {
                echo 'I am running in docker'
                sh 'docker ps'
            }
        }
    }
}

### Yukarıdaki scripti detaylı biçimde inceyelecek olursak Jenkins’te pipeline scriptleri pipeline {} bloğu ile başlıyor. Daha sonra bu blok içerisinde tanımlamalar yapılabiliyor. Örnek olarak biz agent none diyerek herhangi bir agent seçimi yapmadığımızı belirtiyoruz, bu şu demek oluyor pipeline’da agentlarıdaha sonra ihtiyacıma göre seçebiliriz.Stages bloğu içinde koşacak stage’leri implement ediyor olacağım, örnek olarak oluşturduğumuz pipeline-test job’ında sadece 1 adet stage bulunuyor. Stage boğu içinde agent tanımı yapıyorum burada kullanacağım agent bir docker agent’ıdır 


## Jenkins Credentials Export
### İlk olarak target Jenkins serverimizi stop ediyoruz.
###
### Current serverimizdeki credentials.tgz klasörünü target serverimizdeki tmp klasörüne kopyaliyoruz.
###  docker cp .\credentials.tgz dest:/tmp

### Target serverimize bash komutu ile bağlanıyoruz.
###  docker exec -it targetserver bash

### identity.key.enc klasörünü bulup siliyoruz
###   find / -name identity.key.enc
###   rm /var/jenkins_home/identity.key.enc
### credentials.tgz klasörünü jenkins_home dizinine kopyalıyoruz.
###  cp /tmp/credentials.tgz /var/jenkins_home/
### Dizine geçiyoruz
### cd /var/jenkins_home/
### Aşağıdaki komutu girip restrat ettikten sonra credentiali export etmiş oluruz.
### tar xzvf ./credentials.tgz -C ./

## Jenkins Users Export
### Current service'deki users.xml içindeki tanımlı kullanıcıları kopyalayıp target service içindeki users.xml dosyası içine yapıştırarak user export edilebilir.
### User.xml içindeki bir kullanıcı görünümü:
### <entry>
      <string>denemeuser</string>
      <string>denemeuser_12678411654488774791</string>
    </entry>
    
### Jenkins Job Export
### Current Service'deki jobs folderının altında olan job'u kopyalayıp Target Service içine yapıştırarak Job Export yapılabilir.

      
## Jenkins Export Config.xml
### Current Service'deki config.xml dosyası kopyalanıp Target Service içine yapıştıralarak gerçekleştirilir.

## Jenkins Export Nodes
### Current Service'de yaratılan node Target Service içine yapıştırlarak export edilir.

### Docker-Compose kullanarak da aşağıdaki gibi job export edilebilir.
version: '3.8'
services:
  jenkins-src:
    image: jenkins/jenkins
    container_name: src
    user: root
    ports:
       - 85:8080
       - 40000:50000
    volumes:
      - ./volume/src/jenkins_home:/var/jenkins_home  
      
      

  jenkins-dest:
    image: jenkins/jenkins
    container_name: dest
    user: root
    ports:
       - 1950:8080
       - 50000:50000
    volumes:
      - ./volume/dest/jobs:/var/jenkins_home/jobs
      - ./volume/dest/users:/var/jenkins_home/users
      - ./volume/dest/nodes:/var/jenkins_home/nodes
      - ./volume/dest/config.xml:/var/jenkins_home/config.xml

      
      
      




