# Yazıları hızlı bir şekilde web sitesinde yayınlamak 13:15
## Akışı sağlamak

Bence üretim sürecinin en önemli safhalarından bir tanesi uygun akışı sağlamak. Uygun akışı sağlamak için de mümkün oldunca pürüzsüz bir alan oluşturmak ve bu alanı her seferinde daha iyiye götürecek adımları atmak. Biraz üstü kapalı bir anlatım gibi oldu farkındayım. 

Bu web sitesiyle ilgili amacımda mümkün olduğunca az efor sarfederek ortamı pürüzsüzleştirmek ve hızlı bir şekilde web siteme içerik girmekti. Bunu yapabilmek için yayın sürecininde bulunan tüm işleri mümkün olduğunca kolaylaştırmam gerektiğini düşündüm. Bunu yapabilmek için de web sitemi mevcut md (markdown) dosyalarından beslenen bir kaynağa bağlamam gerektiğini düşündüm. Hımm. belki bir bir cloud servisi! Hem yazıların birer yedeklerini de tutmuş olurdum. 

## Wordpress - Git it Write

Web sitemde yazı yayınlamak için wordpress'i kullanıyorum. O yüzden ilk önce Wordpress ile bunu nasıl yapabileceğime baktım ve eklentiler sayfasında  [[Git it Write]] adında bir eklenti buldum. Kullanmak için uygun gibi gözüktü.


## Selam GitHub
Bu eklenti cloud tarafında GitHub'a ihtiyaç duyuyordu. O yüzden bende GitHub üzerinde yeni bir proje açoluşturdum ve branch'in adını **master** olarak değiştirdim. Normalde **main** olarak oluşuyor bu ilk branch ve bundan dolayı yaşadığım bir sorunu çözmem açıkcası biraz vaktimi aldı 🤨. Daha sonra bu GitHub üzerinde projenin ayarlar kısmından **Webhooks** sayfasına girdim ve yeni bir webhook ekledim. 

## GitHub ayarları
Webhooks ayarları
```git
URL: https://github.com/mrsarac/mustafasarac-blog/settings/hooks/
Payload: https://mustafasarac.com/wp-json/giw/v1/publish
Content type: JSON
Secret: **** <- buraya rasgele bir parola yazdım
Just the `push` event.
```


## Wordpress eklenti ayarları
Wordpress tarafında da aşağıdaki ayarlamaları yaptım.

Wordpress Settings
```
Webhook secret: **** <- github'a yazdığım rasgele parolo şeyi
Github username/owner: mrsarac <- benim gitHub profilim
Repository name: mustafasarac-blog <- oluşturduğum projenin adı
Folder to publish from: published <- yayınlayacağım dosyaların bulunacağı klasör
```


Burada verdiğim KEY'i rasgele salladım. "Git it write" eklentisinin ayarlar sayfasında da bu anahtarı kullandım / kaydettim. Böylelikle bendeki master ile web sitem arasındaki ilişkiyi kurmuş oldum.

Belki ilk okuyuşta biraz karışık gelebilir. Ama şimdi anlatınca basit gibi geldi bana. 

## Biraz terminal

 Terminalden projeyi çağırdım.
```
git clone git@github.com:mrsarac/mustafasarac-blog.git <- projenin git URL'i
```


Daha sonrada dosyalarımı 'published' klasöründe olacak şekilde kaydettim ve git'e gönderdim.

 Git'e dosya gönderelim.
```
git commit -m "GitHub üzerindeki ilk yazım"
```


Ve gönderdiğim dosya anında yayınlandı.

## Küçük bir ek
Senkronize olmasında sıkıntılar çıksada; bence iyi çalışıyor gibi. Bu sorunu da bir dosyayı 'değiştirdikten' sonra olduğunu farkettim. Dosyaları oluştururken sıkıntı olmuyor ama web sitesi tarafında mevcut yazılar üzerinde güncelleme yapmıyordu. Bende pluginin kendi yönetim sayfasında bulunan aşağıdaki link üzerinden güncelleme komutunu çağırarak üstesinden geldim.

## Bu kadar
Bu yazıyıda ilk yazım olarak bu senkronizasyon dosyasına bırakıyorum ve git commit'i yapıyorum.


## Bazı testler 🤓
Bağlantılar için [GitHub](http://github.com)
Kod:
```
[GitHub](http://github.com)
```

Resim için 
[alt text](image-0001.png "This is a pic")
Kod:
```
[alt text](image-0001.png "This is a pic")
```

