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

    7.3 Good Routine Names --- İyi Rutin İsimler