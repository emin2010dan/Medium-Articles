<div>

# Yapay Zekalı Virüsler: Gelen Fırtına ve Hazırlık

</div>

Kırk yıllık güvenlik deneyiminin perspektifinden bir uyarı

------------------------------------------------------------------------

### Yapay Zekalı Virüsler: Gelen Fırtına ve Hazırlık

*Kırk yıllık güvenlik deneyiminin perspektifinden bir uyarı*

Bu makalenin İngilizce versiyonu için: \[[AI-Powered Viruses: The Coming
Storm and How to
Prepare](https://medium.com/p/9653ed8dd423)\]

<figure id="7d3e"
class="graf graf--figure graf-after--p graf--trailing">
<img src="./images/88734e1d2c47f830792e46390c4723c4d11efefe.jpg"
class="graf-image" ![]( ./images/1_-O7IwB-9G6N29Lx__cYoIg.jpeg)
data-width="2304" data-height="1792" />
</figure>

------------------------------------------------------------------------

### Bunu Daha Önce Yaşadım

1980\'lerin ortasıydı. Herkes disketten program paylaşıyordu. Kimse bir
şeyin yanlış gidebileceğini düşünmüyordu. Sonra virüsler çıktı.

O zamanlar devletin kritik bir merkezinde teknik müdürdüm. Antivirüs
firmaları yoktu, standartlar yoktu, el kitabı yoktu. Bir ekip kurdum,
kurumları tek tek gezdik, temizlik yaptık. Paniği elimizle tuttuk.
Formatlayıp yeniden başlatmaktan başka çaremiz yoktu. İnsanlar tüm
verilerini kağıttan elle girdi.

O zamanlar bilgisayar olmadan da hayat bir şekilde sürüyordu.

Şimdi süremez.

Bugün benzer bir eşikte duruyoruz. Ama bu sefer tehdidin ölçeği farklı.
Ve hazırlık için penceremiz daralıyor.

------------------------------------------------------------------------

### Oyunu Değiştiren Şey: Açık Kaynak YZ'nin PC'lere İnmesi

Eğer yapay zeka sadece büyük veri merkezlerinde çalışan dev modeller
olsaydı, bu makaleyi yazmıyordum. O senaryoda YZ virüs, ancak büyük
devletlerin rakip devletlere karşı kullanabileceği bir silah olurdu.
Kontrollü, izlenebilir, içine bir yerde durdurucu kod konmuş.

Ama Ollama, LLaMA, Mistral ve benzerleri sıradan PC'lere indi. Herkes
indirebiliyor, herkes çalıştırabiliyor, herkes eğitebiliyor. Bu, silahın
fabrikasını mahalle bakkalına koymuş gibi.

Bütün oyun burada değişti.

------------------------------------------------------------------------

### Mevcut Savunmanın Neden Yetersiz Olduğu

### İmza Tabanlı Yaklaşımın Yapısal Sınırı

Klasik antivirüsler dosyalarda bilinen imzaları arar. Bir virüsü daha
önce gördüyse tanır. Daha önce görmemişse göremez.

YZ virüs kendini hızla değiştirebilir. İmza bırakmaz. Benzerlik
bırakmaz. Bu sorunun farkındalar; bu yüzden modern antivirüsler davranış
analizi, kaynak kullanım izleme, anormal hareket tespiti gibi yöntemlere
geçti.

Doğru yön. Ama bir adım geride.

### Sandbox Paradoksu: Savunma, Saldırıyı Eğitiyor

Bir virüs yakalandığında antivirüs onu sandbox'a alır, merkeze gönderir,
analiz eder, sistemi günceller. Bu mantıklı bir döngü.

YZ virüs için değil.

Sadece tek bir açığı yoklamak için üretilmiş küçük bir virüs düşünün.
Sandbox onu yakaladığında, annesine şu mesajı göndermiş oluyor: *bu kapı
kapalı, başka bak.* Savunma mekanizması, farkında olmadan bir keşif
protokolüne dönüşüyor.

Ne kadar gelişmiş antivirüs, o kadar hızlı ve verimli keşif.

### Davranış Analizi, Davranış Olmadığında Kör

Mevcut YZ destekli antivirüsler anormal davranış arıyor. Peki virüs
anormal davranmıyorsa?

YZ virüs sisteme sızdığında klasik virüs hareketleri yapmayacak. Sabırlı
olacak. Kaynak kullanımını fark edilmeyecek düzeyde tutacak. Asıl kodunu
hiç kullanmayacak. Küçük, birbirinden bağımsız "çocuklar" üretecek. Bu
çocuklar farklı saldırılar deneyecek, başarılı olanlar anneye rapor
edecek.

Davranış tabanlı savunma, davranış olmadığında tamamen kör.

### YZ'lerin Güven Modelinin Manipülasyonu

Üç hafta önce bir Ubuntu güvenlik yazılımı arıyordum. Sorduğum tüm
YZ'ler beni istisnasız aynı yere yönlendirdi: tanınmış bir programcının
kişisel kütüphanesi. Adam gerçekten güvenilir, alanında bilinen biri,
kötü geçmişi yok. Pek çok blog onu referans göstermiş, binlerce beğeni
almış.

Algoritma için mükemmel sinyal. Ben kaynağından indirmeyi seçtim ama
çoğu insan indirmedi.

Şunu düşünün: birkaç günlük yoğun çalışmayla YZ'leri kendi kütüphanenize
yönlendirebilirsiniz. Bloglar yazılır, beğeniler toplanır, referanslar
oluşur. YZ'ler bu sinyali güvenilirlik olarak işler. Günü gelince tek
bir güncellemeyle binlerce sisteme ulaşırsınız.

Kimse ne olduğunu anlayamaz.

------------------------------------------------------------------------

### Makine Kodu Katmanı: Görünmez Tehdit

Python veya C dünyasında düşünen bir güvenlik mühendisi, makine kodu
dünyasında eğitilmiş bir virüsün ne yapabileceğini tahmin edemez.

**Rowhammer** bunu somutlaştırıyor. Bir bellek adresine defalarca
yazarak bitişik hücrelerin değeri fiziksel olarak değiştirildi. Donanım
düzeyinde, yazılımın hiç dokunmadığı bir alanda. Bunu yapan kod hiçbir
antivirüsün işaretleyeceği bir şey yapmıyor, sadece belleğe yazıyor.

Son dönemde açıklanan bazı Linux açıkları da aynı katmanda. Bellekteki
bir dosyaya yetkisiz yazma, oradan yetki yükseltme. İşletim sisteminin
güvenlik modelinin görmediği yer.

YZ virüs bu katmanda çalışırsa antivirüs göremez bile. Çünkü antivirüs
işletim sistemi üzerinde çalışıyor. Donanım katmanında olup biteni
izleyemiyor.

WiFi antenine sızıp gönderilen ve alınan datayı analiz ederek yan
odadaki kişilerin konumunu tespit etmek zaten başarıldı. Makine kodu
dünyasında "imkansız" kelimesini dikkatli kullanmak gerekiyor.

------------------------------------------------------------------------

### Nasıl Hazırlanılabilir

Şunu baştan kabul etmek gerekiyor: ilk savunma hatlarının hızla düşmesi
büyük ihtimal. Bu kabul edilmeden gerçekçi bir savunma planı yapılamaz.

### Erken Uyarı Mekanizması

En kritik ihtiyaç, ilk cephenin düştüğünü anlamak. Virüs sessiz hareket
eder. Fark edilmeden şirketin her köşesine yayılmış olursa savaşacak
vakit kalmaz.

Ne değiştiğini görebilen bir mekanizma şart. Teknoloji her gün değiştiği
için bunun tam biçimini söylemek güç. Ama normal davranıştan sapmaları
izleyen, anomaliyi erkenden sinyalleyen bir yapı olmadan diğer her şey
anlamsız.

### Saldırgana Tanıdık Zemin Verme

1990\'larda ana sistemimi içi boş Linux'larla sardım. Sadece tek
portları dışarı açıktı, içlerinde virüsün yapışabileceği yazılımlar
silinmişti. Beyaz hacker firmalar firewall arkasından saldırdığında bile
savunabildim.

Standart ortam, standart saldırıyı davet eder. YZ virüs de önce ortamı
tanımaya çalışacak. Beklenmedik bir mimariye girdiğinde uyum süreci
uzar, bu süre savunmaya yarar.

### Güç Dağılımı Mimarisi

Tek bir süper kullanıcı yetkisi olmayan sistemler. Yasama, yürütme,
yargı ayrımı gibi, hiçbir bileşenin tüm gücü toplamadığı bir
yetkilendirme modeli. Bu size özel olmalı, standart olmamalı. Saldırgan
beklemediği bir ortamda bulursa adaptasyon süresi uzar.

### Aşı Tesisi Konsepti

Savunma sadece zaman kazandırır. Asıl hedef aşı geliştirmek.

Bu tesisler şu özelliklere sahip olmalı:

- [Dış dünyadan tam fiziksel izolasyon. Stuxnet'in İran'a nasıl
  ulaştığını hatırlayın; USB bile güvenli değil.]
- [Bağımsız elektrik üretimi. Elektrik kablosu bile bir kanal
  olabilir.]
- [Faraday kafesi. Elektromanyetik izolasyon.]
- [Birden fazla tesis, birbirinden bağımsız. Çünkü biri ele geçirilirse
  kapatmanız gerekecek.]

Bu tesislerde birden fazla, birbirinden farklı mimaride YZ antivirüs
çalışmalı. Farklı öğrenme yöntemleri, farklı yapılar. Çünkü tek mimariye
mahkum olursanız tek tip aşı üretebilirsiniz.

### Kademeli Eğitim Zorunluluğu

Bir halterci birden 100 kg kaldıramaz. Önce 20, sonra 30, sonra 50.

YZ antivirüsler de aynı şekilde eğitilmeli. Saldırı başladığında hazır
olmayan bir sistemi aniden cepheye sürmek onu yok eder. Şimdiden eğitime
başlanmalı.

------------------------------------------------------------------------

### Zaman Çizelgesi

Savunma sıralaması şöyle düşünülebilir:

İlk savunma hatları düşerken erken uyarı sistemi çalışıyor, aşı
tesisleri devreye giriyor. Ana savunmalar tek tek gerilirken aşı
geliştirme sürüyor. Son savunma düşmeden aşı hazır olmalı.

General Kış gibi bir müttefikiniz yok. Zamana güvenemezsiniz.

------------------------------------------------------------------------

### Son Söz

Radyumu keşfedince altın haplara koyup zenginlere canlandırıcı diye
satanlar vardı. Sigaranın hamile kadınlara faydalı olduğunu söyleyen
doktorlar vardı. Nükleer santralin tüm savunma sistemini kapatıp deney
yapanlar vardı.

"İnsanlar bu kadar aptalca bir şey yapar mı?" sorusunun yanıtını tarih
defalarca verdi.

Açık kaynak YZ'lerin PC'lere inmesi, bu tehdidi demokratikleştirdi.
Artık sadece büyük devletler değil, motivasyonu olan herhangi biri bu
süreci başlatabilir.

Tehdit modeli teorik değil. Teknik altyapı bugün mevcut. Motivasyon her
zaman var.

Hazırlık için pencere açık. Ne kadar süre açık kalacağını kimse
bilmiyor.

------------------------------------------------------------------------

*Yazar, 1980\'lerin ortasında devletin kritik bir bilgi işlem merkezinde
teknik müdür olarak görev yapmış, Türkiye'nin ilk bilgi işlem güvenlik
standartlarının yazılmasına katkıda bulunmuş ve sonraki on yıllarda
güvenlik alanındaki gelişmeleri aktif olarak takip etmiştir.*

By [Emin](https://medium.com/@emin2010dan) on [May 9,
2026](https://medium.com/p/8cea2a1bce13).

[Canonical
link](https://medium.com/@emin2010dan/yapay-zekal%C4%B1-vir%C3%BCsler-gelen-f%C4%B1rt%C4%B1na-ve-haz%C4%B1rl%C4%B1k-8cea2a1bce13)

Exported from [Medium](https://medium.com) on June 12, 2026.
