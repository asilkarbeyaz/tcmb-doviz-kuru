# tcmb-doviz-kuru #
# Türkiye Cumhuriyet Merkez Bankası Güncel Efektif Döviz Kuru

- Güncel Döviz Kuru verilerini internette bulmamız çok basittir. Peki bu bilgileri doğru ve etkili olarak nasıl kullanabiliriz sorusunu sizlere açıklamak ve uygulamalı olarak göstermek adına oluşturduğum <b>Türkiye Cumhuriyet Merkez Bankası Güncel Efektif Döviz Kuru</b> scripti dilediğiniz gibi kullanabilirsiniz. 
- Kolay ve anlaşılır olabilmesi adına kod (php) içeriğini olabildiği kadar minimize etmeye çalıştım.Umarım işinize yarar.
- Scriptin satışını yapmadığınız ve ticari kullanmadığınız sürece sorun olmayacaktır.
- Soru ve önerileriniz için lütfen iletişime geçiniz ve sosyal medya hesaplarımdan beni takip etmeyi unutmayınız.

<b>[DEMO için Tıklayınız](http://asilkarbeyaz.com/doviz)</b>

## Kullanımı ##

Veri kaynak URL [TCMB Kurlar Sayfası](http://www.tcmb.gov.tr/kurlar/today.xml).

İlgili kaynak bağlantıdan alınan xml içeriği:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml-stylesheet type="text/xsl" href="isokur.xsl"?>
<Tarih_Date Tarih="11.01.2019" Date="01/11/2019"  Bulten_No="2019/8" >
	<Currency CrossOrder="0" Kod="USD" CurrencyCode="USD">
			<Unit>1</Unit>
			<Isim>ABD DOLARI</Isim>
			<CurrencyName>US DOLLAR</CurrencyName>
			<ForexBuying>5.4242</ForexBuying>
			<ForexSelling>5.4340</ForexSelling>
			<BanknoteBuying>5.4205</BanknoteBuying>
			<BanknoteSelling>5.4422</BanknoteSelling>
			<CrossRateUSD/>
			<CrossRateOther/>...
```
# İlk olarak XML kaynak bağlantıdan 
```php 
<?php 
$doviz = simplexml_load_file('http://www.tcmb.gov.tr/kurlar/today.xml'); ?> 
``` 
yöntemi ile verileri  okuma işlemi yapıyoruz.

# XML kaynağından veri okuma işlemi:
```php 
<?php 
$doviz = simplexml_load_file('http://www.tcmb.gov.tr/kurlar/today.xml');
    

// dolar starts //  
$dolar_alis = $doviz->Currency[0]->BanknoteBuying;
$dolar_satis = $doviz->Currency[0]->BanknoteSelling;
//dolar ends //

 
//euro starts // 
$euro_alis = $doviz->Currency[3]->BanknoteBuying;
$euro_satis = $doviz->Currency[3]->BanknoteSelling;
//euro ends // 

//pound starts //
$pound_alis = $doviz->Currency[4]->BanknoteBuying;
$pound_satis = $doviz->Currency[4]->BanknoteSelling;
//pound ends //

?> 
``` 
-Yukarıda görüldüğü gibi sadece DOLAR,EURO ve INGILIZ STERLINI için verileri okuyoruz.
## Sources

* [Jerry Jones](https://codepen.io/jeryj/) (Thank You) ↓
* ↑ [Flexbox Grid Cards with Action Menus](https://codepen.io/jeryj/pen/AXVRXJ)
* [TCMB](http://www.tcmb.gov.tr/kurlar/today.xml) →




## Author

* [Asil Karbeyaz](https://github.com/asilkarbeyaz)
* [Linkedin](https://www.linkedin.com/in/asilkarbeyaz)
* [Instagram](https://instagram.com/asilkarbeyaz)
* [Website](http://asilkarbeyaz.com)
- Bir teşekkür için lütfen takip etmeyi unutmayınız.


<b>[DEMO için Tıklayınız](http://asilkarbeyaz.com/doviz)</b>
