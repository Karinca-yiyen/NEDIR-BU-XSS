# Otomotik Keşif

Neredeyse tüm Web Uygulaması Güvenlik Açığı Tarayıcıları genellikle iki tür tarama yapar: İstemci tarafı kodunu olası DOM tabanlı güvenlik açıkları açısından inceleyen Pasif Tarama ve sayfa kaynağında yük enjeksiyonu yoluyla bir XSS'yi tetiklemeye çalışmak için çeşitli türde yükler gönderen Aktif Tarama. Bu tür araçlar genellikle web sayfalarındaki giriş alanlarını belirleyerek, çeşitli türlerde XSS yükleri göndererek ve ardından aynı yükün bulunup bulunmadığını görmek için işlenmiş sayfa kaynağını karşılaştırarak çalışır; bu da başarılı bir XSS enjeksiyonunu gösterebilir. Yine de bu her zaman doğru olmayacaktır çünkü bazen aynı yük enjekte edilmiş olsa bile çeşitli nedenlerden dolayı başarılı bir yürütmeye yol açmayabilir, bu nedenle XSS enjeksiyonunu her zaman manuel olarak doğrulamamız gerekir. 

XSS keşfinde bize yardımcı olabilecek yaygın açık kaynaklı araçlardan bazıları XSS ​​Strike , Brute XSS ve XSSer'dir

XSS Strike kullanacağız;

Öncelikle indirmek için;

    git clone https://github.com/s0md3v/XSStrike.git

Daha sonra XSS Strike dosyasına giriyoruz;

    cd XSStrike

Gereklilikleri yüklüyoruz.

    pip install -r requirements.txt

Artık çalıştırabiliriz

    python xsstrike.py

Örnek kullanım;

    python xsstrike.py -u "http://SERVER_IP:PORT/index.php?task=test" 

# Manuel Keşif

Manuel XSS keşfi söz konusu olduğunda, XSS açığını bulmanın zorluğu web uygulamasının güvenlik düzeyine bağlıdır. Temel XSS açıkları genellikle çeşitli XSS yüklerini test ederek bulunabilir, ancak gelişmiş XSS açıklarını belirlemek gelişmiş kod inceleme becerileri gerektirir. 
