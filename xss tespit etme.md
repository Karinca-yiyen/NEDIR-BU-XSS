# BASİT ŞEKİLDE XSS TESPİTİ

Basit yolla XSS temel payloadla test edebiliriz:

<script>alert(window.origin)</script>

Kodun çalışıp çalışmadığını sayfayı yeniledikten sonra sayfa URL’si ile birlikte açılır:

https://139.14.177.78:5566 

Başarılıysa ctrl-u ile daha da doğrulayabiliriz.

Örnek:
      <div></div><ul class="list-unstyled" id="todo"><ul><script>alert(window.origin)</script></ul></ul>

ÖNEMLİ!!!

*Birçok modern web uygulaması kullanıcı girdisini işlemek için çapraz alan IFrame'leri kullanır, böylece web formu XSS'e karşı savunmasız olsa bile, ana web uygulamasında bir güvenlik açığı olmaz.

Bu nedenle window.originuyarı kutusunda belli bir değer yerine değerini gösteriyoruz 1. Bu durumda, uyarı kutusu yürütüldüğü URL'yi ortaya çıkarır ve bir IFrame kullanılıyorsa hangi formun savunmasız olduğunu doğrular.

1 varsa bu bir xss olabilir fakat bazı amaları var.*
