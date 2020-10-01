# nuxtjsnav
nuxt.js Navigation Responsive Component  🖖

- NuxtJs projelerinde kullanabileceğiniz navigation componentleri.
- Repositoryden kondları inceleyebilir indirip projenize component olarak dahil edebilirsiniz.
- NPM'den paket olarak yükleyerek kullanabilirsiniz.

- ** Bootstrap kullandığım için projeye bootstrap dahil etmelisiniz.


# NPM
- npm'den yüklemek için : 
```
npm i nuxtjsnav 
```
### npm'den paket olarak projeye yükledikten sonra yapılması gerekenler:
-  Import için 
```nuxt.js 
import Navigation from "../node_modules/nuxtjsnav/Navigation"; 
```
-  data içerisine : 
```nuxt.js  
data() {
    return {
      mobileTitle : "tahirbattal.com.tr", // İçerik örnek olarak veridi. Değiştirerek kullanabilirsiniz.
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
- component olarak tanıtın : 
```nuxt.js
components: {
    Navigation
  },
 ```
 -  Template içinde tag olarak kullanıp menu elemanlarını gönderin : 
 ```nuxt.js
 <Navigation :mobileTitle="mobileTitle" :mainItem="this.mainItem" :menu="this.menu" />
 ```
 -  Logo eklemek için static klasörünün için de image adında bir klasör oluşturun ve içine `logo.png` isimli image ekleyin.


