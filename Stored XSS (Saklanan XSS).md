# Stored XSS (Saklanan XSS)

# GİRİŞ

Tanım:

Kötü amaçlı script, bir veritabanı veya sunucuya kalıcı olarak kaydedilir. Başka bir kullanıcı bu veriyi görüntülediğinde, zararlı kod çalışır.

Senaryo:

Bir sitede input(yorum) bölümü var. Saldırgan input(yorum) kısmına en basit haliyle şu kodu yazar:

html

<script>alert('Stored XSS!');</script>

Eğer site bu kodu filtrelemeden kaydeder ve başka kullanıcılar bu yorumu görürse, onların tarayıcılarında da bu alert penceresi açılır.

TEHLİKELER:

Kullanıcının çerezlerini çalmak(stealing user cookies)

Hesap ele geçirme(account stealing)

Sayfayı başka bir siteye yönlendirme(open redirect)
