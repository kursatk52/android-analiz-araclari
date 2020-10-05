# <span style="color:red"> Android Analiz Araçları

Araçları indirmek için araçların üzerilerine tıklayabilirisiniz.

- [apktool](https://ibotpeaches.github.io/Apktool/install/)
  - Apk dosyasının içini açmamızı sağlıyor. Apk dosyası aslında zip dosyasından farksız fakat normal unzip programları ile açarsanız büyük ihtimal karşınıza çıkan dosyaların içeriği okunamaz halde olacaktır. Bu araç apk dosyası içindeki bu dosyaları okunabilir bir şekilde açmaktadır.
  - Ayrıca apk dosyasını açabildiği gibi açılmış dosyaları tekrar apk dosyası haline getirebilmektedir.  
   </br>
  <img src="https://connortumbleson.com/content/images/2017/06/apktool-logo_1491x543-1.png" alt="drawing" width="500"/>
  </br></br>
- [dex2jar](https://github.com/pxb1988/dex2jar)
  - Apk tool ile açılmış javanın derlenmiş hali olan dex dosyasını tekrar .jar uzantılı hale getirir.
  </br></br>
- [jd-gui](http://java-decompiler.github.io/)
  - .jar uzantılı dosyayı decompile ederek java kodlarını görmenizi sağlar.
  </br></br>
  <img src="http://java-decompiler.github.io/img/jd-gui.png" alt="drawing" width="500"/>
  </br>
- [jadx](https://github.com/skylot/jadx): Bir başka decompiler.
 </br></br>
  <img src="https://i.imgur.com/h917IBZ.png" alt="drawing" width="500"/>
  </br>
- [Burpsuite](https://portswigger.net/burp)
   - Uygulama çalışırken arka planda istekte bulunduğu sunuculara gönderdiği ve sunucudan gelen paketleri yakalayıp üzerinde değişiklik yapmamızı sağlayan gelişmiş bir proxy aracıdır. </br>
   <img src="https://portswigger.net/cms/images/b8/85/12895e89aab9-twittercard-enterprise_logo_-_twitter.png" alt="drawing" width="500"/>
   </br>
- [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb.html)
   - Akıllı android cihazını USB ile bağladığınızda, sanalda olabilir, akıllı telefon ile bilgisayar arasında bağlantıyı sağlar. Böylece telefondaki işlemleri bilgisayardan konsol üzerinden yapılmasını sağlar.
   - Kısaca windows için cmd, linux için terminal ne ise android içinde adb odur.
    </br> </br>
   <img src="https://www.movilzona.es/app/uploads/2020/03/adb-y-fastboot-android-01.jpg" alt="drawing" width="500"/>

-[Mobil Security Framework (MobFS)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
  - Kaynak kod üzerinde full otomatik olarak statik kod analizi yapar. Böylece kod içinde bulunan zafiyetleri, kötü amaçlı alanlar bulur.
  </br></br>
<img src="https://cloud.githubusercontent.com/assets/4301109/20019521/cc61f7fc-a2f2-11e6-95f3-407030d9fdde.png" alt="drawing" 
width="500"/>
</br></br>
- [Androgurad](https://github.com/androguard/androguard)
   - Bir başka kod analizi yapan araç. 
   </br></br>
    <img src="https://raw.githubusercontent.com/androguard/androguard/master/assets/CI/banner.png" alt="drawing" width="500"/>

---
---
---
---
---

# <span style="color:red">Araçların Basit Kullanımı</span>

### apktool

    apktool d <apk>
Apk dosyasını decode ederek açar ve içeriği bulunduğu dizine çıkarır.

    apktool b <apk-dizin>
Dizindeki dosyaları apk olarak paketler.



### dex2jar
    d2j-dex2jar <apk>
**\<apk>-dex2jar.jar ismiyle.jar** uzantılı çıktı verir.


### adb
-     adb shell
    - Android cihazının komut satırına erişim sağlar. Karşıda komut çalıştırmak için kullanılır.     
		 -     pm list packages
		      Kurulu uygulamaları listeler.</br></br>
         -     pm path <paket-ismi>
              Uygulama dosyalarının bulunduğu dizinleri listeler.</br></br>
         -     am start
         	  Aktivite başlatır.</br></br>
         -      am start service
              Servis başlatır.</br></br>
         -     am broadcast
              Yayın gönderir.</br></br>
-     adb devices
    - Açık durumda olan cihazları listeler.</br></br>
    
-     adb pull <cihazdaki-konum> <yereldeki-dizin>
	- Cihazdaki dosyayı PC'ye gönderir.</br></br>    

-     adb push <yereldeki-dizim> <cihazdaki-dizin>
	- Bilgisayardaki dosyayı cihaza gönderir.</br></br>

-     adb install <apk>
    - apk dosyasını cihaza yükler.</br></br>

-	  adb uninstall <uygulama-ismi>
 	- Uygulamayı cihazdan siler.</br></br>

-     adb logcast
    - Log kayıtlarını listeler.</br></br>

-     exit
    - **adb shell** komutu ile açılan shelli kapatır.</br></br>
 
-     adb -s <cihaz-ismi> <komut>
    - Birden fazla cihaza bağlı ve açık olduğu durumlarda komutun uygulanacağı cihazı seçmek için kullanılır.

----
----
----
----
----

# <span style="color:red">Bazı önemli dizinler</span>

-     /data/app
	- Uygulamaların bulunduğu dizin. Buradan adb komutları ile uygulamalarının apk dosyalarını indirebiliriz.

- 	  /system/app ve /system/priv-app
	- Sistem uygulamalarının bulunduğu dizin. Buradan adb ile uygulamalarının apk dosyalarını indirebiliriz ancak **root** yetkisinde olmamız gerekiyor.

-	  /sdcard
	- SD Kart dizini.
