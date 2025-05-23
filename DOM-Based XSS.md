# DOM-Based XSS

# GİRİŞ

TANIM:

Bu türde zararlı kod, doğrudan tarayıcıda çalışan JavaScript tarafından işlenir. Yani saldırı, tamamen istemci (client) tarafında gerçekleşir.

Senaryo:

javascript

var search = location.hash.substring(1);

document.getElementById("result").innerHTML = search;

Bir kullanıcı şu URL'ye giderse:

php-template

https://kerem.com/#<img src=x onerror=alert('DOM XSS')>

Script şu şekilde çalışır:

html

<div id="result">
  
  <img src=x onerror=alert('DOM XSS')>
  
</div>

Tehlikeler:

Web sayfasının işlevlerini manipüle etme(DOM Manipulation)

DOM’u kötüye kullanarak veri çalma

# GELİŞME 

Bir diğer Non-persitant(Sunucuda kalıcı olarak saklanmayan) XSS türüdür fakat Reflected XSS ile aralında bazı farklar vardır.

Reflected XSS giriş verilerini HTTP istekleri aracılığıyla arka uç sunucusuna gönderirken, DOM XSS tamamen JavaScript aracılığıyla istemci tarafında işlenir.

DOM XSS, JavaScript'in . aracılığıyla sayfa kaynağını değiştirmek için kullanıldığında oluşur Document Object Model (DOM).

Örnek:

Firefox Geliştirici Araçları'ndaki sekmeyi açarsak ve testöğeyi yeniden eklersek, hiçbir HTTP isteğinin yapılmadığını fark ederiz.

URL'deki giriş parametresinin "#" eklediğimiz öğe için bir hashtag kullandığını görüyoruz, bu da bunun tarayıcıda tamamen işlenen bir istemci tarafı parametresi olduğu anlamına gelir. Bu, girişin JavaScript aracılığıyla istemci tarafında işlendiğini ve asla arka uca ulaşmadığını gösterir; bu nedenle bir DOM-based XSS.

Buna neden olan binevi Sink’tir kullanıcı girdisini sayfadaki bir DOM Nesnesine yazan işlevdir. İşlev Sink kullanıcı girdisini düzgün bir şekilde temizlemezse, bir XSS saldırısına karşı savunmasız olur.DOM nesnelerine yazmak için yaygın olarak kullanılan JavaScript işlevlerinden bazıları şunlardır:

document.write()

DOM.innerHTML

DOM.outerHTML

jQuery Ayrıca, DOM nesnelerine yazan kütüphane fonksiyonlarından bazıları şunlardır:

add()

after()

append()

Eğer bir Sink fonksiyon herhangi bir temizleme işlemi yapmadan (yukarıdaki fonksiyonlar gibi) tam olarak girdiyi yazıyorsa ve başka bir temizleme yöntemi kullanılmıyorsa, o zaman sayfanın XSS'e karşı savunmasız olması gerektiğini biliyoruz. 

    document.getElementById("todo").innerHTML = "<b>Next Task:</b> " + decodeURIComponent(task);

Yukaridaki kodda girdiyi kontrol edebildiğimizi ve çıktının temizlenmediğini görebiliyoruz, bu durumda bu sayfa DOM XSS'e karşı savunmasız olmalı.

# DOM SALDIRILARI

Daha önce kullandığımız XSS payload'unu denersek(<script>alert(document.cookie)</script>), yürütülmeyeceğini göreceğiz. Bunun nedeni, fonksiyonun güvenlik özelliği olarak içindeki innerHTMLetiketlerin kullanımına izin vermemesidir, bunun yerine farklı bir paylaod deniyoruz.

    <img src="" onerror=alert(window.origin)>

Bu kod resim bulamadığında ki her zaman bulamıcak çünkü sayfada resim olmadığını varsayıyoruz alert'i çalıştıracak boş bir resim bağlantısı kullandığımız için " " ayarlamaya veya kullanmaya gerek yoktur.
