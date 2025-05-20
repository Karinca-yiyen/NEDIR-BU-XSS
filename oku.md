# NEDİR BU KÜTÜPHANE🐜
Bu proje farklı kaynaklardan alınan bilgilerin kısa ve öz bi şekilde notların tutulmuş halidir.

kısa ve anlaşılır.

bölüm bölüm.

eğlenceli.

# 🐜 XSS NEDİR?
XSS, açılımı Cross-Site Scripting olan, yani “siteler arası betik çalıştırma” anlamına gelen bir güvenlik açığıdır. Bu açık sayesinde kötü niyetli kişiler, bir web sitesine zararlı JavaScript kodları enjekte edebilir.

Kısaca: Bir sitede sana ait olmayan kod çalıştırıyorsan, orada XSS olabilir!

# 🐜 NASIL ÇALIŞIR?
Düşün ki bir web sitesine yorum yazıyorsun. Ve inputa normalde şöyle yazarsın:

Harika bir karınca!
Ama bir saldırgan şöyle yazabilir:

<script>alert('Karınca burada!');</script>
Eğer site bunu filtresiz yayınlarsa, sayfayı ziyaret eden herkesin ekranına bir uyarı kutusu çıkar! Bu sadece basit bir örnek, saldırgan bu yolla:

Oturum çalabilir 🍪

Kullanıcıyı kandırabilir 🎭

Başka sitelere yönlendirme yapabilir 🚪

🐜 XSS TÜRLERİ
Stored XSS (Kalıcı XSS)
Zararlı kod veritabanına kaydedilir. (Yorum, profil bilgisi...)

Reflected XSS (Yansıtmalı XSS)
Zararlı kod link ile gönderilir. Kullanıcı linke tıklayınca çalışır.

DOM-based XSS
Zararlı kod JavaScript ile DOM üzerinde işlenirken çalışır. Sunucu değil, tarayıcı tarafında olur.

🐜 BASİT ÖRNEK
Bir arama kutusu olduğunu düşün:

Aradığınız: <script>alert('Karınca geldi!');</script>
Eğer site bunu doğrudan gösterirse, kullanıcıyı korkutacak, belki kandıracak şeyler yapılabilir.

# XSS öğren
NEDIR-BU-XSS ile XSS’si daha iyi anlayıp öğrenebilirsiniz
# TÜRKÇE
