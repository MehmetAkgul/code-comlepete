7) High-Quality Routines.... Yüksek Kaliteli Rutinler 
Yüksek kalitede rutinleri olşturmayı 7 başlıkta ele almıştır.
    7.1)Valid reasons to create a routine 
    7.2)Design  at the routine level
    7.3)Good routine Names
    7.4)How long can a routine be?
    7.5How to use routine parameters
    7.6)Special considerations in the use of fonctions
    7.7)Macro routines and inline routines

    Bu başlıkladan bence en önemlisi Good Routine Name olanı, çünkü burada isim vermek kodunuza açıklama eklemenin en uygun yolu gereksiz satır içi açıklamaları ortadan kaldırmaktadır.

    "Bilgisayarın kendisi bir yana, rutin, bilgisayar bilimindeki en büyük buluştur." küçük parçalar isviçre çakısındaki gibi sorunsuz çalışsın işimizi halletsin.

    "Rutin aynı zamanda yerden tasarruf etmek ve performansı artırmak için şimdiye kadar icat edilmiş en büyük tekniktir."

    Bir rutin tekrarlanan bir kodun tekrarlanmasının onüne geçmek için tasarlandı ise olabildiğince doğrudur.    

    7.1)Valid reasons to create a routine  -- Bir Rutin Oluşturmak için Geçerli Nedenler
    
            a) Reduce complexity                   -- Karmaşıklığı azaltın
                "Hakkında düşünmenize gerek kalmaması ve bilgileri gizlemek için bir rutin oluşturun"
                
                Buradaki temel neden bir rutini yazarız yeri gelince kullanırız ama o ne yapıyor diye tekrar dönüp bakamyız çünkü çalışıyor.

            b) Make a section of code readable     -- Kodun bir bölümünü okunabilir hale getirin
                "Kodun bir bölümünü iyi adlandırılmış bir rutinini içine yerleştirme, kodun amacını belgelemenin en iyi yollarından biridir."


            c) Avoid duplicate code                -- Yinelenen kodlardan kaçının
                "Şüphesiz, bir rutin oluşturmanın en popüler nedeni, yinelenen kodlardan kaçınmaktır. Aslında, iki rutinde birbirine benzer kodların oluşturulması, ayrıştırmada bir hata anlamına da gelir."

                Dikkat edilmesi gereken kısım rutinlerin içindeki kod tekrarıdır ve buda yeni bir rutin oluşturma sebebidir.

            d) Hide sequences                      -- Dizileri gizle
                "Olayların işlendiği sırayı gizlemek iyi bir fikirdir."

                "Örneğin, bir program tipik olarak kullanıcıdan veri alıyorsa ve ardından bir dosyadan da yardımcı veri alıyorsa, ne kullanıcı verilerini alan rutin ne de dosya verilerini alan rutin, hangi rutinin önce gerçekleştirilmesine bağlı olmamalıdır."
                
            e) Hide pointer operations             -- İşaretçi işlemlerini gizle
                İşaretçi şu şekilde açılanabilir. 
                    İşaretçi Operatörleri
                    * ve & işaretçileriyle kullanılan iki özel operatör vardır. &, işleneninin bellek adresini döndüren tekli bir operatördür, 
                        konumu=&denge;
                    "konumu" değişkenine "denge" değişkeninin değerinin bellek adresini koyar. Bu adres, "denge" değişkeninin bilgisayardaki dahili bellekte bulunan konumudur. "denge" değişkeninin değeri ile ilgisi yoktur. "Konumu" değişkeni, "denge" değişkeninin adresini aldığı için ifadeler sözlü olarak ifade edilebilir. 

                    İkinci operatör *'dır ve &'nin tamamlayıcısıdır. Değişkenin operand tarafından belirtilen adresteki değerini döndüren tekli bir operatördür. Aşağıdaki örneği düşünün:
                        degeri=*denge;
                    Bu işlem, "denge" değişkeninin değerini "degeri" değişkenine çevirecektir.
                    
                    Ayrıntılı bilgi için: https://web1.eng.famu.fsu.edu/~haik/met.dir/hcpp.dir/notes.dir/cppnotes/node68.html
                
            f) Improve portability                 -- Taşınabilirliği geliştirin
                "Rutinlerin kullanımı, taşınabilir olmayan yetenekleri yalıtır, gelecekteki taşınabilirlik çalışmalarını açıkça tanımlar ve yalıtır."
                
            g) Simplify complicated boolean tests  -- Karmaşık haldeki boole testlerini basitleştirin
                "Böyle bir testi bir fonksiyona koymak, kodu daha okunaklı hale getirir çünkü
                    (1) testin detayları yolun dışındadır,
                    (2) açıklayıcı bir fonksiyon ismi testin amacını özetler.."

            h) Improve performance                 -- Performansı geliştirin
                "Kodun tek bir yerde olması, rutini daha verimli bir algoritmayla veya assembler gibi daha hızlı, daha verimli bir dilde yeniden kodlamayı pratik hale getirir."

            i) To ensure all routines are small?   -- Tüm rutinlerin küçük olmasını sağlamalımıyız?
                "Aslında, bazı işler tek bir büyük rutinde daha iyi gerçekleştirilir."



            Operations That Seem Too Simple to Put Into Routines --- Rutinlerin içine koymak için oldukça basit görünen işlemler

            "İki veya üç satır kod içerecek şekilde bütün bir rutin oluşturmak, fazladan bir şey gibi görünebilir. Ancak deneyim, iyi bir küçük rutinin ne kadar yararlı olabileceğini gösteriyor."

            Summary of Reasons to Create a Routine --- Bir Rutin Oluşturmak için Nedenlerin Özeti
                Reduce complexity               --  Karmaşıklığı azaltın
                Make a section of code readable --  Kodun bir bölümünü okunabilir hale getirin
                Avoid duplicate code            --  Kodun bir bölümünü okunabilir hale getirin
                Hide sequences                  --  Sırayı gizle
                Hide pointer operations         --  İşaretçi işlemlerini gizle
                Improve portability             --  Taşınabilirliği iyileştirincomputation
                Simplify complicated boolean tests--  Karmaşık boole testlerini basitleştirin
                Improve performance             --  Performans geliştirme
                Isolate complexity              --  Karmaşıklığı izole et
                Hide implementation details     --  Uygulama ayrıntılarını gizle
                Limit effects of changes        --  Değişikliklerin etkilerini sınırlayın
                Hide global data                --  Küresel verileri gizle
                Make central points of control  --  Merkezi kontrol noktaları yapın
                Facilitate reusable code        --  Yeniden kullanılabilir kodu kolaylaştırın
    

    7.2 Design at the Routine Level --- Rutin seviyesindeki tasarım
        "Rutinler için uyum , bir rutindeki işlemlerin rutinle ne kadar yakından ilişkili olduğunu ifade eder. Bazı programcılar “güç” terimini tercih eder" 
        
        Güçlü rutin gibi... 
        "Amaç, her rutinin bir şeyi iyi yapması ve başka hiçbir şey yapmamasıdır."
        
        "Tabii ki, bağlılıklarının bu değerlendirmesi, rutinlerin adlarının söylediklerini yaptığını varsayar - eğer başka bir şey yaparlarsa, daha az tutarlı ve kötü adlandırılmışlardır."

        eğer rutin ismiyle aynı işi yapıyorsa uyumlu değilse dercesine göre uyumsuz olabilir.

           1) Genellkile uyumlu kabul edilen rutin türleri: 
                a) Sequential cohesion-- Sıralı uyumlu rutinler
                "Sıralı uyumun bir örneği, doğum tarihi verilen bir çalışanın yaşını ve emeklilik zamanını hesaplayan bir rutindir."
                önce yaşı hesaplayıp sonra çıkan sonuçla emekliliği hesaplıyorsa bu sıralıdır.

                b) Communicational cohesion   --- İletişimsel uyumlu rutinler 
                "...bir rutindeki işlemler aynı verileri kullanır ve başka hiçbir şekilde ilişkili değildir"
                yukarıdaki örnekten devam edelim 
                önce yaşı hesaplayıp sonra onceki dataları kullanmadan doğrum tarihi ile tekrardan emekliliği hesaplıyorsa bu iletişimsel olarak uyumlu bir rutindir.

                c) Temporal cohesion --- geçici uyumlu rutinler 
                "...işlemlerin hepsi aynı anda yapıldığından ve bir rutinde birleştirildiğinden ismeine Geçici Uyumlu rutin denir."

                "...operasyonları doğrudan yerine getirmek yerine, belirli aktiviteleri gerçekleştirmek için diğer rutinleri geçici olarak uyumlu rutine çağırmaktır."
            
           2) Kalan uyum türleri genellikle kabul edilemez.
            
                a) Procedural cohesion  --- işlem olarak uyumlu rutinler
                "...çünkü bir dizi işlemi belirli bir sıraya koyar ve işlemlerin başka herhangi bir nedenle birleştirilmesine gerek yoktur."
                "Daha iyi uyum sağlamak için ayrı işlemleri kendi rutinlerine yerleştrimelisin."

                b) Logical cohesion  --- mantıksal uyumlu rutinler  
                açıklama :|Kontrol bayrakları, her modül aracılığıyla başarılı bir girişimin veya başarısız bir girişimin nasıl işlendiğini gösterir. | ***https://docs.oracle.com/cd/E19683-01/806-4078/secauth-223/index.html****

                "birkaç işlem aynı rutine doldurulur ve işlemlerden biri, geçirilen bir kontrol bayrağı tarafından seçilir."

                "Buna mantıksal uyum denir çünkü rutinin kontrol akışı veya "mantığı" işlemleri birbirine bağlayan tek şeydir - hepsi büyük bir "if" ifadesinde veya " case "  ifadesinde bulunur."

                c) Coincidental cohesion --- tesadüfi uyumlu rutinler
                "...bir rutindeki işlemlerin birbirleriyle fark edilebilir bir ilişkisi yoktur. Diğer iyi isimler “uyumsuzluk” veya “kaotik uyum”dur."

    7.3 Good Routine Names --- İyi Rutin İsimleri
        "Bir rutin için iyi bir isim, rutinin yaptığı her şeyi açıkça tanımlar."
        Fakat rutinde olan herşey isminde yazmaz, aksine tam olarak yaptığı şey ile isimlendirilmelidir.
        
        HandleCalculation(), PerformServices(), ProcessInput(), and DealWithOutput()gibi rutin ismleri bize ne yptığını söylemiyor.
        
        "HandleOutput(), FormatAndPrintOutput() ile değiştirilirse, rutinin ne yaptığı hakkında oldukça iyi bir fikriniz olur."

        Değer dödüren rutinler değerleri ile adlandırılmalıdır. "cos(), customerId.Next(), printer.IsReady()" gibi.

        İSimlendirme yaparken "verb-plus-object name (fiil-artı-nesne adı)" kuralına da uymalıyız. 
            ---NOT---
            Nesne yönelimli dillerde, nesnenin kendisi çağrıya dahil edildiğinden, prosedür adına nesnenin adını eklemeniz gerekmez.
            ---NOT---
       
        Zıtlıkları tam olarak kullanın.
            ●	add/remove
            ●	begin/end
            ●	create/destroy
            ●	first/last
            ●	get/put
            ●	get/set
            ●	increment/decrement
            ●	insert/delete
        gibi.

        Ortak işlemler için adlandırma kuralları
        "Bazı sistemlerde, farklı işlem türleri arasında ayrım yapmak önemlidir. Bir adlandırma kuralı, genellikle bu ayrımları belirtmenin en kolay ve en güvenilir yoludur."


    7.4 How Long Can a Routine Be? ---- Bir Rutin Ne Kadar Uzun Olabilir?    

        Teorik olarak 66 ila 132 satır olarak tanımlanır.
        "4.000 satır uzunluğunda kod hatta 12.000'den daha fazla satır uzunluğunda rutinler gördüm"
         ---NOT---
            Nesne yönelimli programlardaki rutinlerin büyük bir yüzdesi, çok kısa olacak olan erişimci rutinleri olacaktır.
         ---NOT---
         "Yaklaşık 200 satırdan uzun rutinler yazmak istiyorsanız dikkatli olun.200 satır kodu geçerken bir üst anlaşılabilirlik sınırına girmek zorundasınız."

    7.5 How to Use Routine Parameters -----Rutin Parametreleri Nasıl Kullanılır
        
        a) Parametreleri (input-modify-output) sırasına koy 
        b) Kendi giriş ve çıkış anahtar kelimelerinizi oluşturun 
        c) Birkaç rutinde benzer parametreler kullanılıyorsa, benzer parametreleri   tutarlı bir sıraya koyun. 
            "Windows rutinlerinin çoğu ilk parametresi olarak "handle" önekini alır ve hatırlanması kolaydır."
        d) Tüm parametreleri kullan 
            "Bir rutine bir parametre iletirseniz, onu kullanın. Kullanmıyorsanız, parametreyi rutin arayüzden kaldırın. Kullanılmayan parametreler artan hata oranı ile ilişkilidir."
        e) Durum veya hata değişkenlerini en sona koy
        f) Çalışma değişkenleri olarak rutin parametreleri kullanmayın (başka bir değişkene ata öyle devam et)
        g) Parametrelerle ilgili belge arayüzü varsayımları
            "Rutininize aktarılan verilerin belirli özelliklere sahip olduğunu varsayarsanız, varsayımları yaparken belgeleyin."
            
            Ne tür arayüz varsayımları?
                I)   Parametrelerin yalnızca giriş, değiştirilmiş veya yalnızca çıkış olup olmadığı
                II)  Sayısal parametre birimleri (inç, fit, metre vb.)
                III) Numaralandırılmış türler kullanılmıyorsa durum kodlarının ve hata değerlerinin anlamları
                IV) Beklenen değer aralıkları
                V)  Asla görünmemesi gereken belirli değerler

        h) Bir rutinin parametre sayısını yaklaşık yedi ile sınırlayın 
            "Yedi, insanların kavrayışı için sihirli bir sayıdır. Psikolojik araştırmalar, insanların genellikle aynı anda yaklaşık yedi parçadan fazla bilgiyi takip edemediklerini bulmuştur."
        i) Parametreler için bir giriş, değişiklik ve çıkış adlandırma kuralı düşünün
        j) Arayüz soyutlamasını sürdürmek için rutinin ihtiyaç duyduğu değişkenleri veya nesneleri iletin gönderin
            "Her seferinde aynı nesneden gelen parametrelerle rutine giden parametre listesini sık sık değiştirirseniz, belirli öğeler yerine tüm nesneyi rutine geçemeniz gerektiğinin bir göstergesidir."
        k) Kullanılan adlandırılmış parametreler
        l) Parametre geçiş mekanizması hakkında hiçbir şey varsaymayın
            "Parametreler genellikle bir sistem yığınına iletilir, ancak dillerin kullandığı tek parametre geçiş mekanizması bu değildir. Yığın tabanlı mekanizmalarda bile, parametrelerin kendileri farklı sıralarda iletilebilir ve her parametrenin baytları farklı sıralanabilir. Parametrelerle doğrudan uğraşırsanız, programınızın farklı bir makinede çalışmayacağını neredeyse garanti edersiniz."
        m) Gerçek parametrelerin resmi parametrelerle eşleştiğinden emin olun
        

    7.6 Special Considerations in the Use of Functions --- Fonksiyonların Kullanımında Özel Hususlar
        "İşlev, bir değer döndüren bir rutindir; bir prosedür olmayan bir rutindir."

        a) Bir İşlevin Ne Zaman Kullanılacağı ve Bir Prosedürün Ne Zaman Kullanılacağı
            "Bir işlev yalnızca girdi parametrelerini alır ve tek değerini işlevin kendisi aracılığıyla döndürür. sin(), CustomerID() ve ScreenHeight() gibi işlev her zaman döndürdüğü değere göre adlandırılır." 
            
            "Öte yandan, bir prosedür de girdi, değiştirme ve çıktı parametrelerini alabilir."

            "Kısacası işlevin asıl amacı; adında belirtilen değeri döndürmekse ozaman bu bir rutindir, aksi takdirde bu bir prosedürdür."
        b) İşlevin Dönüş Değerini Ayarlamak
            - Tüm olası dönüş yollarını kontrol edin,
            - Yerel verilere referansları veya işaretçileri döndürmeyin. Eğer hiç veri dönmüyorsa hata almamak için varsayılan bir değeri dönderin

    7.7 Macro Routines and Inline Routines --- Makro Rutinler ve Satır İçi Rutinler
        a) Makro ifadelerini tamamen parantez içine al
            i)  Çok ifadeli makroları küme parantezleriyle çevreleyin
            ii) Gerektiğinde rutinlerle değiştirilebilmeleri için rutinler gibi kodu genişleyen makroları adlandırın
        b) Makro Rutinlerinin Kullanımına İlişkin Sınırlamalar (örnekler C++ için)
            ● "const" --- Sabit değerleri bildirmek için
            ● "inline" -- Satır içi kod olarak derlenecek işlevleri tanımlamak için 
            ● "template"- min, max vb. gibi standart işlemleri tür açısından güvenli bir şekilde tanımlamak için 
            ● "enum" --- Numaralandırılmış türleri tanımlamak için 
            ● "typedef"- Basit tür değiştirmeleri tanımlamak için 
        c) "Inline" Satır İçi Rutinler 
                "C++ bir "inline" anahtar sözcüğü destekler. "inline" bir rutin programcıya, kod yazma zamanında kodunu bir rutin olarak ele almasına izin verir. Ancak  derleme zamanında, derleyici, rutinin her bir örneğini satır içi koda dönüştürecektir. Teori olarak satır içi (inline)'ler rutin çağrı ek yükünü önleyen yüksek verimli kod üretmeye yardımcı olabilir."

        
       KONTROL LİSTESİ: Yüksek Kaliteli Rutinler
        Büyük Resim Sorunları
            a) Rutini oluşturma nedeniniz yeterli mi?
            b) Kendi rutinlerinini içine eklenmekten fayda sağlayacak olan rutinin diğer tüm bölümleri kendi rutinlerine içine eklendi mi?
            c) Rutinin adı, bir prosedür için: güçlü, net bir "verb-plus-object name" fiil + nesne adı mı, yoksa bir işlev için, dönüş değerinin açıklayan bir ad mı?
            d) Rutinin adı, rutinin yaptığı her şeyi açıklıyor mu?
            e) Ortak işlemler için adlandırma kuralları oluşturdunuz mu?
            f) Rutinin güçlü, tek bir şeyi yapan ve onu iyi yapan, işlevsel bir uyuma sahip mi?
            g) Rutinlerde "loose coupling" var mı? Rutinin diğer rutinlerle olan bağlantıları küçük, samimi, görünür ve esnek mi?
            h) Rutinin uzunluğu, yapay bir kodlama standardı yerine doğal olarak işlevi ve mantığıyla mı belirleniyor?

        Parametre Gönderme Sorunları
            a) Bir bütün olarak alınan bir rutinin parametre listesi tutarlı bir arayüz soyutlaması sunuyor mu?
            b) Benzer rutinlerdeki parametrelerin sırasını eşleştirmek de dahil olmak üzere, rutinin parametreleri mantıklı bir sırada mı?
            c) Arayüz ile ilgili varsayımlar belgeleniyor mu?
            d) Rutin yedi veya daha az parametreye mi sahip?
            e) Her giriş parametresi de kullanılıyor mu?,
            f) Her bir çıkış parametresi de kullanılıyor mu?
            g) Rutin, giriş parametrelerini çalışma değişkenleri olarak kullanmaktan kaçınıyor mu?
            h) Eğer rutin bir fonksiyon ise, tüm olası durumlarda geçerli bir değer döndürüyor mu?

 