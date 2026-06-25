# Modüler Bir Yapay Zeka Mimarisine Doğru: Uzmanlaşmış Biliş, Belirsizlikten Arınmış Temsil ve Dinamik Vektör Uzayları

*Yeni Nesil Yapay Zeka Sistemleri için Kavramsal Bir Çerçeve*

**Tartışma Makalesi**

Emin • Katkıda Bulunan: Claude (Anthropic)

2026

---

### Özet

*Günümüzün büyük dil modelleri (BDM'ler), edebi yaratıcılığı, görsel hayal gücünü ve bilimsel akıl yürütmeyi tek bir monolitik mimari içinde birleştirmeye çalışmaktadır. Bu makale, böyle bir birleştirmenin sadece verimsiz olmadığını, aynı zamanda her alanın gerektirdiği farklı bilişsel yapılarla temelden uyumsuz olduğunu öne sürmektedir. Üç temel bileşenden oluşan katmanlı, modüler bir yapay zeka ekosistemi öneriyoruz: (1) doğal dildeki belirsizliği çözen ve diller arası girdiyi belirsizlikten arınmış bir iç temsile normalleştiren bir Çevirmen YZ; (2) her biri kendi alanına uygun temsiller üzerinde çalışan alana özel Akıl Yürütme YZ motorları —bilimsel, edebi ve görsel— ve (3) vektör boyutluluğunun her terimin kavramsal karmaşıklığına ve alan derinliğine göre ölçeklendiği dinamik bir vektör-uzayı modeli. Nörobilim, dilbilim, bilgi teorisi ve bilgisayar tarihinden analojilerden yola çıkarak, uzmanlaşmanın —genelleşmenin değil— hem daha yetenekli hem de daha yorumlanabilir yapay zeka sistemlerine giden yol olduğunu savunuyoruz. Günümüz BDM'lerinde sıkça görülen halüsinasyon problemi, bir eğitim hatası olarak değil, birbiriyle uyumsuz bilişsel kipleri tek bir temsil uzayına sıkıştırmanın mimari bir kaçınılmazlığı olarak yeniden çerçevelenmektedir.*

### 1. Giriş

Modern yapay zeka araştırmaları cazip bir hedefin ardından gitmiştir: her şeyi yapabilen tek bir model. GPT-4, Gemini ve Claude şiir yazabilir, diferansiyel denklemler çözebilir, kod üretebilir ve resimleri tanımlayabilir —bazen aynı yanıt içinde. Bu çok yönlülük etkileyicidir, ancak nadiren eleştirel olarak incelenen bir bedeli vardır.

Bir beyin uzmanının roman yazmaya çalıştığını ya da ünlü bir şairden kuantum alan teorisi türetmesinin istendiğini düşünün. Bir alan için optimize edilmiş bilişsel yapılar, diğer alanla aktif olarak çakışır. Nörobilim, bilimsel akıl yürütme ile yaratıcı bilişin birbirinden farklı ve bazen birbirine karşıt sinirsel ağlara dayandığını çok önceden kabul etmiştir. Prefrontal korteks sistematik mantıksal çıkarımı yönlendirir; varsayılan mod ağı ise çağrışımsal, metaforik ve anlatısal düşünceyi yönlendirir. Bir alandaki üstünlük, diğer alandaki üstünlükle zayıf —bazen negatif— bir ilişki gösterir.

Mevcut yapay zeka mimarileri bu dersi tamamen göz ardı etmektedir. Tek bir transformer'ı insan üretiminin tüm yelpazesi üzerinde —bilimsel makaleler, romanlar, kod, fıkralar, hukuki belgeler ve günlük konuşma— eğiterek, her alanda vasat olan ama bu vasatlığın alanlar arasında ortalamaya alındığı için fark edilmesi zor olan sistemler üretiyoruz. Bu sistemleri rahatsız eden halüsinasyonlar düzeltilmesi gereken hatalar değildir; daha derin bir mimari kategori hatasının belirtileridir.

Bu makale, dilin, anlamın ve bilginin gerçekte nasıl yapılandığına dair bir dizi düşünceden ortaya çıkan alternatif bir vizyon geliştirmektedir. Yeni nesil yapay zeka sistemlerinin, çeviri, akıl yürütme ve üretim arasında açık bir mimari ayrım içeren ve her bilişsel alanın yapısal gereksinimlerine uyan temsil şemalarına sahip monolitik modeller yerine modüler ekosistemler olması gerektiğini öne sürüyoruz.

### 2. Yapay Zeka Temsilinde Çok Anlamlılık (Polisemi) Problemi

#### 2.1 Bir Kelime, Birçok Dünya

"Işık" kelimesi bu sorunu sıra dışı bir açıklıkla göstermektedir. Fizikte ışık, dalga boyu, frekans, foton enerjisi ve yayılma hızı ile karakterize edilen elektromanyetik bir olgudur. Şiirde ışık, anlayış, umut, vahiy veya ilahi varlığın bir metaforudur. Fotoğrafçılıkta ışık pratik bir kaynaktır —yön, sıcaklık, kalite, miktar. Günlük dilde ışık; ağır olmama, karanlık olmama, ciddi olmama veya bir sigara alevi anlamına gelebilir.

İnsan okuyucu bu anlamları zahmetsizce ayırt eder, çünkü bağlamsal ipuçları birden çok bilişsel düzeyde eş zamanlı olarak işlenir: sözdizimsel konum, çevredeki kelime hazinesi, söylem türü, konuşmacı kimliği ve önceki konuşma geçmişi bu sürece katkıda bulunur. Günümüz BDM'leri bu anlam ayırımını istatistiksel olarak yaklaşık şekilde gerçekleştirir —olası anlamlar üzerinde bir olasılık dağılımı atarlar— ancak belirsizliği hiçbir zaman kesin olarak çözmezler. "Işık" için tek bir gömme (embedding) vektörü, bu anlamların tümünü eş zamanlı olarak bir şekilde kodlamak zorundadır; bu da kayıpsız olarak geometrik açıdan imkânsızdır.

Kelime Anlamı Belirsizliğinin Çözülmesi (WSD) alanı bu sorunla onlarca yıldır tatmin edici bir çözüm bulamadan boğuşmaktadır. Biz, WSD'nin monolitik bir mimari içinde temsil düzeyinde çözülemeyeceğini; akıl yürütme katmanı herhangi bir girdi almadan önce devreye giren özel bir belirsizlik-çözme katmanı gerektirdiğini öne sürüyoruz.

#### 2.2 Diller Arası Yapısal Farklılık

Sorun, diller arası girdiyi göz önüne aldığımızda daha da derinleşir. Türkçe, Özne-Nesne-Fiil (SOV) sıralı, eklemeli bir dildir; İngilizce Özne-Fiil-Nesne (SVO) sıralı ve büyük ölçüde yalın (izole edici) bir dildir; Japonca, kapsamlı bağlamsal eksiltme ile konu-yorum yapısı kullanır; Arapça ise kök-kalıp morfolojisiyle yüksek derecede çekimlidir. Bunlar aynı içeriğin sadece farklı sıralamaları değildir —kavramsal yapıyı bölümlere ayırma ve ilişkilendirmenin farklı yollarını yansıtırlar.

Ham Türkçe girdi ile ham İngilizce girdi alan bir Akıl Yürütme YZ'si, kavramsal olarak aynı düşünceler için ayrı temsiller tutmak zorunda kalır. Makine çevirisindeki interlingua geleneği —yüzey dilinden bağımsız, tek bir kanonik anlam temsili üretme— 1990'larda terk edilmiştir, çünkü o dönemki teknoloji yeterli interlingual temsiller oluşturamıyordu. Biz bu terk edilişin erken olduğunu ve ön işleme katmanı olarak çalışan özel bir Çevirmen YZ'nin artık bu temsilleri yeterli doğrulukla oluşturabileceğini öne sürüyoruz.

### 3. Çevirmen YZ: Belirsizliğin Çözülmesi ve Normalleştirme

#### 3.1 Rol ve Sorumluluklar

Çevirmen YZ, insan doğal dili ile Akıl Yürütme YZ motorlarının kullandığı iç temsil sistemi arasındaki sınırda yer alır. Sorumlulukları şunlardır:

- **Anlam belirsizliğinin çözülmesi:** Çok anlamlı bir kelimenin bağlam içinde hangi anlamı taşıdığını belirlemek ve onu belirsizlikten arınmış bir iç token ile değiştirmek (örn. ışık → LIGHT_PHYSICS_PHOTON veya LIGHT_LITERARY_METAPHOR).
- **Sözdizimsel normalleştirme:** Herhangi bir girdi dilinin yüzey sözdizimini, o dile özgü kelime sırası kurallarını ortadan kaldırarak kanonik bir mantıksal forma çevirmek.
- **Alan etiketleme:** Sorguyla ilgili bilgi alanını/alanlarını belirlemek ve normalleştirilmiş temsili uygun Akıl Yürütme YZ motoruna yönlendirmek.
- **Üslup ve niyet sınıflandırması:** Örneğin, olgusal bir bilimsel sorgu ile duygusal olarak ifade edici bir edebi istek arasında ayrım yapmak, böylece uygun akıl yürütme modu etkinleştirilir.

#### 3.2 Başlangıç (Bootstrap) Problemi

Doğal bir itiraz ortaya çıkar: dili belirsizlikten arındırmak için Çevirmen YZ'nin kendisinin de dili —belirsizlikleri dahil— anlaması gerekir. Bu döngüsel görünmektedir. Biz, belirsizliğin çözülmesi ve akıl yürütmenin farklı tolerans profillerine sahip ayrı bilişsel işlemler olduğunu belirterek bu sorunu ele alıyoruz. Çevirmen YZ'nin anlam konusunda olasılıksal belirsizlik taşımasına açıkça izin verilir —sadece bu belirsizliği, Akıl Yürütme YZ'sinin kesin belirsizlikten-arınmışlık gerekliliğinin ihlal edileceği eşiğin altına indirmesi gerekir. %95 oranında doğru anlamdan emin olan bir Çevirmen YZ, operasyonel olarak yeterlidir; Akıl Yürütme YZ'sinin kalan belirsizliğe asla maruz kalmasına gerek yoktur.

Çevirmen YZ'nin kontrollü belirsizliğe tolerans gösterdiği, Akıl Yürütme YZ'sinin ise hiçbir belirsizliği kabul etmediği bu iş bölümü, yetenekli bir tercümanın çok taraflı bir konferansta çalışma şekline benzetilebilir: tercüman bazen konuşmacının iki olası okumadan hangisini kastettiğinden belirsiz olabilir, ancak seslendirmeden önce kesin bir seçim yapar ve resmi kayda hiçbir zaman belirsizlik iletmez.

### 4. Dinamik Vektör Uzayları ve Bilginin Galaksi Modeli

#### 4.1 Sabit Boyutluluk Problemi

Mevcut tüm gömme (embedding) modelleri, kavramsal karmaşıklığından bağımsız olarak her token'a sabit boyutlu bir vektör atar. GPT-4 sınıfı modellerde bu boyutluluk 12.000–16.000 civarındadır. "Kedi" kelimesi ile "kuantum kromodinamik asimptotik özgürlük" ifadesi aynı uzunlukta vektörler alır. Bilgi-teorik açıdan bu açıkça optimal değildir: basit, yüksek frekanslı, bağlamsal olarak kararlı kavramlar yeterince temsil edilmek için daha az boyut gerektirirken, karmaşık, alana özgü, bağlama hassas kavramlar daha fazla boyut gerektirir.

Sabit boyutluluk kısıtlaması sağlam mühendislik nedenlerle vardır: matris çarpımı tek tip vektör boyutları gerektirir, GPU paralelliği sabit tensör şekilleri için optimize edilmiştir ve kosinüs benzerliği yalnızca eşit uzunluktaki vektörler için tanımlıdır. Bu kısıtlamalar gerçektir. Önerimiz bunları inkâr etmiyor; aksine, soruyu yeniden çerçeveliyor.

#### 4.2 Galaksi Metaforu

Bir Akıl Yürütme YZ'sinin bilgi uzayını şu özelliklere sahip galaksi-benzeri bir yapı olarak kavramsallaştırmayı öneriyoruz:

- **Çekirdek (galaktik merkez):** Tüm alanların temelini oluşturan kavramlar —temel mantıksal operatörler, temel fiziksel sabitler, ilkel matematiksel nesneler. Bu kavramlar anlamsal olarak kararlıdır, nadiren belirsizdir ve düşük boyutlu temsiller gerektirir.
- **İç yörüngeler:** Alan-genel bilimsel kavramlar —atomik elementler, geometrik ilkeller, temel biyolojik taksonlar. Orta düzeyde boyutluluk, alan-içi çapraz referanslama sık görülür.
- **Dış kollar:** Son derece uzmanlaşmış alana özgü kavramlar —belirli bir otomotiv kaplama formülasyonunun optik yansıtma özellikleri, belirli bir şiirsel geleneğin prozodik kuralları. Yüksek boyutluluk, alanlar arası etkileşim nadirdir.
- **Seyrek kollar-arası bölgeler:** Anlamsal örtüşmesi ihmal edilebilir düzeyde olan, uzak alanlardan kavramlar. Bu bölgeler arasındaki hesaplama sadece gereksiz değildir —aktif olarak yanıltıcıdır da, çünkü ilişkisiz yüksek boyutlu vektörler arasındaki uzaklık ölçütüne gürültü hâkim olur.

#### 4.3 Hesaplamalı Gerçekleştirme

Değişken boyutlu vektörlerin hesaplama açısından elverişli bir çerçeve içinde teknik olarak gerçekleştirilmesi birkaç şekilde ele alınabilir. Projeksiyon katmanları, gerektiğinde çapraz-kavram işlemleri için daha kısa vektörleri geçici olarak genişletebilir, ardından eklenen boyutları işlem sonunda atabilir. Longformer ve BigBird gibi modellerde zaten kullanılan seyrek dikkat (sparse attention) mekanizmaları ilgili bir fikri uygular: her kavramın her diğer kavrama dikkat etmesi gerekmez. GPT-4 ve Gemini'de kullanılan Uzman Karışımı (Mixture-of-Experts, MoE) mimarileri tamamlayıcı bir yaklaşım sunar: farklı girdileri farklı uzman alt ağlara yönlendirerek, "BMW ayna kaplaması" sorgusunun kimya alt ağını hiçbir zaman etkinleştirmemesini (ve bunun tersini) sağlar.

Ancak galaksi modelinin en matematiksel açıdan doğal gerçekleştirimi hiperbolik gömmedir. Hiperbolik uzayda (günümüz gömmelerinde kullanılan düz Öklid uzayının aksine), hiyerarşik ilişkiler —üst kavramdan alt kavrama— katlanarak daha yüksek verimlilikle korunur. Nickel ve Kiela'nın (2017) Poincaré Gömmeleri çalışması, 5 boyutlu bir hiperbolik gömmenin, yüzlerce Öklid boyutu gerektiren hiyerarşik yapıları temsil edebileceğini göstermiştir. Galaksi metaforu, Poincaré diskinin geometrisine doğal olarak haritalanır: merkez en genel kavramları, sınır ise en özel kavramları temsil eder.

#### 4.4 Kavramsal Karmaşıklığın Bir Göstergesi Olarak Sözcüksel Yoğunluk

Uygun vektör boyutluluğunu belirlemek için ilkeli bir yöntem, sıra dışı bir kaynaktan elde edilebilir: bir alanın sözcüksel yoğunluğu. İnuit halkları, kar ve buzun çeşitleri için onlarca farklı terime sahiptir —dilleri rastgele olduğu için değil, o kavramsal uzay içindeki ince ayrımların pratik açıdan önemli olması nedeniyle. Tıp uzmanları, özel terminolojiyle yüzlerce farklı hücre morfolojisini birbirinden ayırt eder. Finans hukuku, günlük dilin "yatırım" diye topladığı araçlar için kesin terimlere sahiptir.

Sözcüksel yoğunluk —bir alanın kavramsal bir uzayı alt bölümlere ayırmak için kullandığı farklı terim sayısı— bu nedenle, o uzayı çakışma olmadan temsil etmek için gereken boyutluluğun doğal bir vekili (proxy) olarak görülebilir. Bir kavram için n özel alt-terime sahip bir alan, bunları çakışmadan ayırt etmek için en az log₂(n) boyut gerektirir; pratikte gereksinim daha yüksektir, çünkü kavramlar birbirleriyle ilişki içinde var olur, bağımsız değildir. Bu ilke, insan etiketlemesine gerek kalmadan vektör boyutluluğu atamak için ampirik temelli, alana hassas bir yöntem sunmaktadır.

### 5. Üç Akıl Yürütme Mimarisi

#### 5.1 Bilimsel Akıl Yürütme YZ'si

Bilimsel Akıl Yürütme YZ'si, Çevirmen YZ tarafından üretilen kanonik iç temsil üzerinde çalışır. Tanımlayıcı özellikleri şunlardır:

- **Anlamsal belirsizliğe sıfır tolerans:** her token tam olarak bir referansa karşılık gelir.
- **Deterministik çıkarım zincirleri:** belirli bir girdi için akıl yürütme yolu tekrarlanabilir ve incelenebilirdir.
- **Alan-bölümlenmiş vektör uzayları:** ilişkisiz alanlardan kavramlar etkileşime girmez, bu da alanlar arası gürültüyü ortadan kaldırır.
- **Kalibre edilmiş belirsizlik:** kanıt yetersiz olduğunda, sistem açık güven aralıklarıyla bir olasılık tahmini döndürür, uydurma bir yanıt değil.

Bu sistemden şiir istemek sadece yararsız değildir —bir kategori hatasıdır ve sistem bunu öyle tanımalı ve isteği yönlendirme için Çevirmen YZ'ye geri göndermelidir.

#### 5.2 Edebi Yaratıcılık YZ'si

Edebi yaratıcılık, Bilimsel Akıl Yürütme YZ'sinin dışladığı özelliklerin tam tersini gerektirir:

- **Üretken belirsizlik:** aynı anda birden çok anlam taşıyan tek bir ifade bir kusur değil, bir özelliktir.
- **Çağrışımsal akıl yürütme:** anlam beklenmedik yan yana getirmelerden ortaya çıkar; sistem, bilimsel bir akıl yürütücünün ilgisiz olarak değerlendireceği kavramsal uzaklıkları aşmalıdır.
- **Kültürel ve tarihsel derinlik:** metaforlar, göndermeler, tonal kayıtlar ve tür gelenekleri birinci sınıf temsil unsurlarıdır.
- **Eksikliğe tolerans:** tam olarak açıklanamayan bir şiir, başarısız bir şiir değildir.

Günümüz BDM'leri teknik açıdan yetkin ama nadiren şaşırtıcı şiirler üretmektedir. Bu, geniş bir derlem üzerinde tahmin hatasını en aza indirmek için eğitilmiş bir sistemden tam olarak beklenecek bir sonuçtur: çıktılar, yüksek olasılıklı devamlara yakınsar. Düşük olasılıklı, anlamsal açıdan yüksek uzaklıktaki bağlantılar için optimize edilmiş özel bir mimariye sahip bir Edebi YZ, niteliksel olarak farklı —ve niteliksel olarak daha zengin— yaratıcı çıktılar üretirdi.

#### 5.3 Görsel Yaratıcılık YZ'si

Görsel yaratıcılık üçüncü, farklı bir durum sunar. Önemli bir tarihsel veri noktası: 1985 yılında bir Apple II üzerinde çalışan, rastgele renkler ve konumlar üreten bir BASIC programı, görsel olarak çarpıcı, gerçek anlamda yaratıcı çıktılar üretebiliyordu. Yaratıcılığı basitliğinden ötürü azalmamıştı; aslında kısıtlamaları —sınırlı palet, ızgara temelli geometri, sistematik değişim— günümüzün metin koşullu görüntü üreticilerinin, çok daha büyük karmaşıklıklarına rağmen sıklıkla eşleştiremediği estetik etkiler üretmişti.

Bu gözlem, görsel yaratıcılığın sembolik dil işlemeye hiç gerek duymayabileceğini ileri sürmektedir. Görsel üretim için temsil altyapısı, dilbilimsel token'lar üzerinde değil, temelde mekânsal ve örüntü temelli olabilir —doku gradyanları, kompozisyonel denge, renk uyumu ve ritim üzerinde işlem yapan bir yapı. Token-gömme hattını tamamen atlayıp doğrudan mekânsal temsiller üzerinde çalışan bir Görsel Yaratıcılık YZ'si, tam da uyumsuz temsil biçimleri arasında çeviri yapmak zorunda olmadığı için metin koşullu modelleri geride bırakabilir.

### 6. Modüler Yapay Zeka Ekosistemi

#### 6.1 Mimari Genel Bakış

Burada önerilen tam mimari şu katmanlardan oluşur:

- **İnsan Arayüz Katmanı:** herhangi bir dilde, herhangi bir üslupta, herhangi bir alanda ham doğal dil girdisi alır.
- **Çevirmen YZ:** belirsizliği çözer, normalleştirir, alan etiketler ve yönlendirir.
- **Akıl Yürütme YZ Motorları (paralel, uzmanlaşmış):** Bilimsel, Edebi, Görsel ve potansiyel olarak diğerleri (Hukuki, Matematiksel, Kişilerarası).
- **Sentez Katmanı:** bir sorgu birden fazla alana yayıldığında, çoklu Akıl Yürütme YZ motorlarının çıktılarını entegre eder.
- **Çıkış Çevirmeni:** iç temsili uygun insan diline ve üsluba geri dönüştürür.

#### 6.2 Mühendislik İlkesi Olarak Sorumlulukların Ayrılması

Yazılım mühendisleri, sorumlulukların ayrılmasını sistem tasarımındaki en güçlü ilkelerden biri olarak kabul eder: her bileşen, bileşenler arasında temiz arayüzlerle, tam olarak bir iyi tanımlanmış işlevden sorumlu olmalıdır. Mevcut monolitik BDM'ler bu ilkeyi toptan ihlal etmektedir: belirsizliğin çözülmesi, akıl yürütme, hafıza erişimi, ton yönetimi, olgusal hatırlama ve yanıt üretimi hepsi aynı farklılaşmamış ağırlık matrisi içinde gerçekleşir.

Burada önerilen modüler mimari, sorumlulukların ayrılmasını bilişsel düzeyde uygular. Her bileşen bağımsız olarak geliştirilebilir, değerlendirilebilir ve iyileştirilebilir. Hatalar yerelleştirilebilir: Bilimsel Akıl Yürütme YZ'si yanlış bir yanıt üretirse, teşhis, Çevirmen YZ'nin ona doğru şekilde belirsizlikten arındırılmış bir temsil sağlayıp sağlamadığıyla veya akıl yürütme motorunun kendisinin başarısız olup olmadığıyla başlar. Bu hata ayıklanabilirlik, günümüz sistemlerinde neredeyse hiç bulunmamaktadır.

#### 6.3 Mimari Bir Belirti Olarak Halüsinasyon

Günümüz BDM'lerindeki halüsinasyon problemi —olgusal olarak yanlış ifadelerin kendinden emin biçimde üretilmesi— eğitim verisi kalitesine, insan geri bildiriminden takviyeli öğrenmedeki hizalama sorunlarına ve yetersiz olgusal temellendirmeye bağlanmıştır. Bu atıflar kısmen doğrudur, ancak daha derin bir nedeni gözden kaçırmaktadır: tek bir mimarinin hem kendinden emin bir olgusal bilgi getirici hem de akıcı bir yaratıcı üretici olması gerektiğinde, bu kipleri, tespit edilmesi zor ve tamamen önlenmesi imkânsız şekillerde harmanlaması kaçınılmazdır.

Bilgi mevcut olmadığında makul görünen metin üretmesi mimari olarak yasaklanmış bir Bilimsel Akıl Yürütme YZ'si —yalnızca "yetersiz kanıt" veya bir olasılık tahmini çıkarabilen bir sistem— sorunlu anlamda halüsinasyon görmez. Halüsinasyon, kendinden emin üretimi evrensel bir çıkış kipi olarak ele alan sistemlerin bir özelliğidir. Bunu ortadan kaldırmak daha iyi eğitim değil, mimari kısıtlama gerektirir.

### 7. Mevcut Araştırmalarla İlişki

Burada önerilen çerçevenin bileşenleriyle birleşen, mevcut araştırmalardan birkaç hat bulunmaktadır; ancak hiçbiri bunları burada tarif ettiğimiz şekilde birleştirmemektedir.

**Hiperbolik gömmeler.** Nickel ve Kiela'nın Poincaré Gömmeleri (NeurIPS 2017) çalışması, hiyerarşik bilgiyi temsil etmek için hiperbolik uzayın üstün verimliliğini göstermiştir. Sonraki çalışmalar bunu daha karmaşık ontolojilere genişletmiştir. Burada önerilen galaksi modeli, doğrudan Poincaré diskinin geometrisinden esinlenmiştir; genellik ekseni, merkeze olan uzaklığa karşılık gelir.

**Uzman Karışımı.** MoE mimarileri (Shazeer ve ark., 2017; GPT-4 ve Gemini'de kullanılmaktadır), alt-ağ düzeyinde alan yönlendirmesini uygular. Önerimiz bunu sistemler-arası düzeye genelleştirir; paylaşılan ağırlıklı uzman modüller yerine tamamen ayrı mimariler kullanır.

**Seyrek dikkat.** Longformer, BigBird ve ilgili modeller, tüm token çiftlerinin karşılıklı dikkate gerek duymadığı sezgisini uygular. Galaksi modeli bunu kavramlar-arası düzeye genişletir: uzak anlamsal alanlardan kavramlar birbirleriyle etkileşime girmemelidir.

**Interlingua.** Makine çevirisindeki interlingua geleneği (1970'ler–1990'lar), dilden bağımsız anlam temsilini hedeflemiştir. Burada önerilen Çevirmen YZ, öncülerinin sahip olmadığı yeteneklerle güçlendirilmiş, bu geleneğin modern bir mirasçısıdır.

**Google Pathways.** Google'ın Pathways mimarisi (Dean, 2021), büyük, paylaşılan bir model üzerinde seyrek etkinleştirme önermiş, farklı girdilerin farklı hesaplama yollarını etkinleştirmesini sağlamıştır. Önerimiz daha radikaldir: paylaşılan bir mimari içinde seyrek yollar yerine, özel bir koordinasyon katmanına sahip tamamen ayrı mimariler savunuyoruz.

### 8. Çıkarımlar ve Açık Sorular

#### 8.1 Yapay Zeka Güvenliği İçin

Akıl yürütme kipleri arasında açık bir ayrıma sahip modüler bir mimarinin önemli güvenlik çıkarımları olabilir. Doğrudan ikna edici doğal dil üretemeyen bir Bilimsel Akıl Yürütme YZ'si, olgusal bilgi getirme ile akıcı üretimin birleştirildiği bir sisteme kıyasla yanlış bilgi, manipülasyon veya yanıltıcı çıktılar üretmeye daha az yeteneklidir. Güvenlik kısıtlamaları, doğal olarak kısıtlanmamış üretken bir sistem üzerinde sonradan eklenen filtreler olarak değil, mimari düzeyde uygulanabilir.

#### 8.2 Yorumlanabilirlik İçin

Yapay zeka yorumlanabilirliğinin önündeki en önemli engellerden biri, günümüz BDM'lerinin tüm bilişsel işlemleri aynı farklılaşmamış etkinleştirme uzayında gerçekleştirmesidir. Bileşenler arasında temiz arayüzlere sahip modüler sistemler, her arayüzde yorumlanabilirliği mümkün kılar: Çevirmen YZ'nin ürettiği iç temsili inceleyebilir, girdiyi doğru şekilde belirsizlikten arındırdığını doğrulayabilir ve Bilimsel Akıl Yürütme YZ'sinin akıl yürütme zincirini ayrıca denetleyebilirsiniz. Bu katmanlı yorumlanabilirlik, uçtan uca kara kutu açıklamasından niteliksel olarak daha ele alınabilirdir.

#### 8.3 Açık Sorular

- Alan sınırlarını aşan kavramlar (kuantum biyolojisi, hesaplamalı dilbilim, hesaplamalı yaratıcılık) galaksi yapılı bir bilgi uzayında nasıl temsil edilmelidir?
- Bir token'ın kavramsal karmaşıklığı ve alan üyeliği, derlem istatistiklerinden otomatik olarak tahmin edilebilir mi, yoksa insan etiketlemesi gerekir mi?
- Çoklu Akıl Yürütme YZ motorlarının çıktılarını entegre eden Sentez Katmanı için optimal mimari nedir?
- Alan sınıflandırması gerçek anlamda belirsiz olan sorgular —örneğin, ışığın doğasıyla ilgili, ne tamamen bilimsel ne de tamamen edebi olan felsefi bir soru— nasıl ele alınmalıdır?

### 9. Sonuç

Monolitik yapay zeka mimarisi yaklaşımının —insan bilişsel üretiminin tüm yelpazesi üzerinde eğitilmiş tek bir model— fark edilmesi zor ve sadece eğitimle tamamen onarılması imkânsız şekilde, her şeyde vasat olan sistemler ürettiğini savunduk. Halüsinasyon problemi, belirsizlik problemi ve yaratıcı yüzeysellik problemi, ortak bir mimari nedenin belirtileridir.

Önerdiğimiz alternatif, bir Çevirmen YZ'nin doğal dildeki belirsizliği çözdüğü ve normalleştirilmiş temsilleri, vektör boyutluluğu alanının yapısal karmaşıklığına göre kalibre edilmiş bir bilgi uzayında çalışan, alana özel Akıl Yürütme YZ motorlarına yönlendirdiği modüler bir ekosistemdir. Bu bilgi uzayının geometrisi galaksi-benzeridir: merkezde derli temsillere sahip temel kavramlar, çevrede daha zengin temsillere sahip uzmanlaşmış kavramlar ve uzak alanlar arasında seyrek etkileşim.

Bu vizyon, çeşitli kaynaklardan gelen içgörülerin birleşiminden beslenmektedir: nörobilimden (farklı bilişsel kipler için farklı sinirsel devreler), dilbilimden (interlingua geleneği ve kelime anlamı belirsizliğinin çözülmesi), bilgi teorisinden (temsil karmaşıklığının bir vekili olarak sözcüksel yoğunluk), bilgisayar tarihinden (kısıtlanmış yaratıcılığın gücüne dair bir vaka çalışması olarak 1985 Apple II BASIC programı) ve yazılım mühendisliğinden (sağlam, yorumlanabilir, sürdürülebilir sistemler için bir tasarım ilkesi olarak sorumlulukların ayrılması).

Gerçek anlamda yetenekli, güvenilir derecede doğru ve güvenli şekilde dağıtılabilir yapay zeka sistemlerine giden yol, daha büyük monolitik modellerden değil, ilkeli uzmanlaşmadan geçmektedir. Doğa bu sonuca milyonlarca yıllık evrim yoluyla ulaştı. Biz bu dersi daha hızlı öğrenebiliriz.

---

**Köken Notu**

*Bu makale, emekli bir bilgisayar mühendisi tarafından sohbet yoluyla geliştirilen fikirlerin yazılı hale getirilmiş biçimidir. Özgün içgörüler —dinamik vektör uzaylarının galaksi modeli, belirsizlik-çözme katmanı olarak Çevirmen YZ, yaratıcı mimarilerin üçlü uzmanlaşması ve boyutluluk ataması için sözcüksel-yoğunluk ilkesi— yapay zeka tasarımındaki temel sorularla olan düşünsel etkileşiminden ortaya çıkmıştır. Yazarın kariyeri, erken kişisel bilgisayar döneminden günümüze uzanan bir bakış açısı sunmaktadır; bu bakış açısı, genç uygulayıcıların nadiren sahip olduğu bir şeydir: basit, iyi kapsamlanmış bir programın tasarlandığı şeyi tam olarak yaptığında ve bunu güzel bir şekilde yaptığında hissettirdiği duygunun hatırası.*
