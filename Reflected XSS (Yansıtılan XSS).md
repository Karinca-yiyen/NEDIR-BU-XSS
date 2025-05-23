# Reflected XSS (Yansıtılan XSS)

                                          
# GİRİŞ

TANIM:

Kötü amaçlı kod, bir link ile birlikte gönderilir ve anında sayfaya yansıtılır, veritabanına kaydedilmez.

Senaryo:

Kullanıcıdan alınan bir parametre, ınput(arama bölümünden)sayfada doğrudan yansıtılıyor:

1.html

https://kerem.com/search?query=<script>alert('Reflected XSS!')</script>

Sunucu bu parametreyi doğrudan sayfaya eklerse:

Kötü niyetli şahış, bu URL’yi bir kullanıcıya sosyal medya yolları veya  gönderdiğinde, script kullanıcı tarayıcısında çalışır.

<script>alert('Reflected XSS!')</script>

kullanıcı istemeden parametreyi çalıştırır.

Kısa ve net şekide 1.html’i saldırgan kendi bilgisiyarına yazdıktan sonra bu html kodunu sosyal medya yoluyla kurbana atar ve bu html kodu saldırganın istediği uzantıda çalışır ve saldırgan Reflected XSS sonucu kurbana saldırıda bulunur.

TEHLİKELER:

Oltalama saldırıları(Pahishing)

Zararlı linklerle kimlik avı

# GELİŞME
                                          
Non-persistent XSS:

Non-persitant XSS kısaca sunucu tarafından kalıcı olarak saklanmaz.

İki tane Non-persitant XSS vardır DOM Based XSS ve Reflected XSS arka sunucu tarafından işlenir.

Reflected XSS arka sunucu tarafından işlenir.

Kalıcı XSS’in aksine Non-persistent XSS geçicidir ve sayfa yenilenince gider bu nedenle yalnızca hedeflenen kullanıcıyı etkiler.

Reflected XSS güvenlik açığı kısaca girdilerimiz arka uç sunucuya ulaştığında temizlenmeden veya filtrelenmeden bize ulaşır.

En temel eğer bir input kısmına karınca değeri girince site bize 'karınca' yazarsa bu XSS’e karşı savunmasız olabilir çünkü filtrelenmemiştir.

Örnek:

Bu gibi seneryoda basit bir script deneyelim <script>alert(window.origin)</script> ve bir uyarı penceresi açılır Görev '' eklenemedi diye bir sonuç
      
Bu durumda scriptimiz kod bloğunun işleyişinden çıkıp kendi kodumuzu enjekte edıyo, bunu düzeltmek için scriptin başına bir ' ekliyoruz ve artık XSS kapandı.
      
Kısaca Non-persitant XSS < > ' " gibi karakterlerin güzel filtrelenmemesinden dolayı oluşur.
      
