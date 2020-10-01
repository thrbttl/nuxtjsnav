# nuxtjsnav

nuxt.js Navigation Responsive Component  🖖

- NuxtJs projelerinde kullanabileceğiniz navigation componenti.
- Repositoryden kondları inceleyebilir indirip projenize component olarak dahil edebilirsiniz.
- NPM'den paket olarak yükleyerek kullanabilirsiniz.

- ** Bootstrap kullandığım için projeye bootstrap dahil etmelisiniz.
- ** Fontawsome kullandığım için projeye fontawsome dahil etmelisiniz. (Açılır menü iconu için.)


# NPM
- npm'den yüklemek için : 
```
npm i nuxtjsnav 
```
### npm'den paket olarak projeye yükledikten sonra yapılması gerekenler:
1. Import için 
```nuxt.js 
import Navigation from "../node_modules/nuxtjsnav/Navigation"; 
```
2. data içerisine : 
```nuxt.js  
data() {
    return {
      mobileTitle : "tahirbattal.com.tr", // Bu Navigation2 için örnek
      mainItem : "Anasayfa",
        // İçerik (Anasayfa) örnek olarak veridi. Değiştirerek kullanabilirsiniz.
      menu : {
        first : "Hakkımda",
        second : "İletişim",
        third : "Blog",
        fifth : "Fortoğraflar",
          // İçerikler 
          //    (first : "Hakkımda",
          //    second : "İletişim",
          //    third : "Blog",
          //    fifth : "Fortoğraflar",) 
          // örnek olarak veridi. Değiştirerek kullanabilirsiniz.
      }
    };
  },
````
3. component olarak tanıtın : 
```nuxt.js
components: {
    Navigation
  },
 ```
 4. Template içinde tag olarak kullanıp menu elemanlarını gönderin : 
 ```nuxt.js
 <Navigation :mobileTitle="mobileTitle" :mainItem="this.mainItem" :menu="this.menu" />
 // :mobileTitle="mobileTitle" (Navigation2 için)
 ```
 5. Logo eklemek isterseniz ```node_modules/nuxtjsnav/NavigationTop``` dosyasının içinde yorum sarıtı olan, 4-6 arası satırları açın. img tagının src'sine ekleyeceğiniz logonun yolunu girin.




