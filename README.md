# rehber

=begin




String
    = işaretinin sağına "xyz" olarak yazılan her şey

Boolean
    * Bir şeyin true veya false olarak tanımlanması için kullanılır
    * Bir değişkenin yanına true veya false yazıldığında artık bu bir boolean değişkenidir
                                        my_boolean = true
                                        mahmut = false

Variables:
    * Değişkenler. Her şey olabilirler. Örneğin soldakiler birer değişken:
                                        my_num = 100
                                        variable1 = ali emre

    * Dikket edilmesi gereken üç şey:     
                                        Sağdakini sola atıyoruz
                                        Bir variable iki değere atanmamalı, atanırsa sondaki geçerli olur
                                        
Commands:
    * print = Yazdığın ne varsa, satır atlamadan ekrana yazar
    * puts = Önce yazar, ardından satır atlar (put string anlamına gelir)

=begin =end:
    * Yorum aracı. Arasındaki her şey yorumdur, code olarak sayılmaz (comment).
    * Bir şeylerden sonra aynı satıra yazılamaz.

Methods:
    * Stringlerin sonuna .xyz şeklinde yazılır. Ard arda birden fazla method yazılabilir.
    * Eğer bir variable her zaman bir methoda bağlı olarak çalışsın istiyorsak, methodun sonuna ! (ünlem işareti) koyuyoruz. Böylece bu variable'ın sonucu hep o method ile çalışıyor.
                                        .reverse = Variable'a bağlı değeri tersine çevirir
                                        .length = Variable'a bağlı değerin kaç haneden oluştuğunu gösterir
                                        .upcase = Variable'a bağlı değeri büyük harfler ile yazar                                    
                                        .downcase = Variable'a bağlı değeri küçük harflerle yazar
                                        .capitalize = Bir string'in ilk harfini büyük harf yapar
                                        .chomp = Ruby'nin her veriden sonra eklediği boş satırı ortadan kaldırmaya yarar
                                        .split = Variable içindeki kelimeleri teker teker ayırır. Yani string alır array verir.
                                            delimiter = Neye göre split yapacağını gösterir. text.split(",") kodu virgül işareti gördüğü yerde texti ayırır
                                        .include? = Aradağı şeyi bulursa true, bulamazsa false sonucunu verdirtir.
                                        .gsub! = Global Substition anlamına gelir. Kullanıcının girdiği stringi (gets ile aldığımız) değiştirmeye yarar.
                                            print "Thtring, pleathe!: "
                                            user_input = gets.chomp
                                            user_input.downcase!

                                            if user_input.include? "s"
                                              user_input.gsub!(/s/, "th")                           # Bu kod, kullanıcının girdiği metindeki her "s" harfini "th" olarak değiştirir
                                            else
                                              puts "Nothing to do here!"
                                            end
  
                                            puts "Your string is: #{user_input}"

                                        .each = Iterator. Bir arrayın içindeki her değeri değiştirmek için kullanılır. Yapılacak işlemin | | arasına yazılması önemlidir. Sonuna end yazılmalı.
                                            array = [1,2,3,4,5]
                                            array.each do |x|             
                                              x += 10                                               # Bu kod, variable içindeki her değere 10 ekliyor
                                              print "#{x}"
                                            end                

                                            odds = [1,3,5,7,9]
                                            odds.each do |x|                                        # Bu kod odds variable içindeki array 'ı iki ile çarpmaya yarıyor
                                                x *= 2
                                                print x
                                            end    

                                        .times = Bir şeyi istediğimiz kadar yazdırmamıza yarar
                                            10.times do print "ha" end                              # Bu kod art arda 10 kere "ha" yazacak

Gets:
    * Kullanıcının bilgi girebileceği alan yaratır. Otomatik olarak sonunda boş satır bırakır.
    * .chomp ile kullanılmasının nedeni bu sondaki satırı ortadan kaldırmaktır.

#
    * Yorum aracı. Sağındakiler yorumdur.
    * Bir şeylerden sonra aynı satıra yazılabilir.

Matematik:
    * +, -, * ve / yanında ** (üs alma) ve % (kalan bulma) fonksiyonu vardır.

String Interpolation
    * Interpolation Türkçe'de "ekleme" anlamına geliyor.
    * #{} içine yazdığımız değişkenleri bir commandın içine gömmeye yarıyor.

if
    * Koşula bağlamak için kullanılır.
    * Sonuna end koymak zorundasın. Diğer türlü koşulu bitirmez
    * if her zaman true değeri arar
                                        if 1 < 2
                                            print "I'm getting printed because one is less than two!"
                                        end

else
    * if 'ten sonra yazdığımız expression doğru değilse yazdırılacak şeyi tanımlar
    * if ve else true değilse çalışır
                                        if "deniz".length < "furkan".length
                                            print "Merhaba"
                                        else                                                        # Aslında if, elsif ve else boolean tanımının kendilerine göre doğru olmasını bekliyor
                                            print "Hoscakal"                                        # else boolean için mümkün bir tanım bulamadığı zaman döndüreceği sonuçtur
                                        end                                  

elsif
    * Her zaman if 'ten sonra gelir
    * Birden çok elsif alt alta yazılabilir
    * elsif her zaman true değeri arar
                                        if "deniz".length > "furkan".length
                                            print "Merhaba"
                                        elsif "deniz".length == "ozgur".length
                                            print "Hoscakal"
                                        else
                                            print "Bir daha dene"
                                        end

unless
    * if 'in tam tersidir.
    * Sonuna end koymak zorundasın
    * unless her zaman false değeri arar
                                        hungry = false

                                        unless hungry
                                          puts "I'm writing Ruby programs!"                         # hungry, false olan bir boolean olarak tanımlandığı için
                                        else                                                        # unless de her zaman false aramaya proglamdığı için
                                          puts "Time to eat!"                                       # Bu sorgy "I'm writing Ruby programs!" dönecek
                                        end
    * != , unless 'in yaptığı işi yapar
                                        is_false = 2 == 3                   
                                            puts is_false                                           # Bu sorgu false sonucunu dönecek

                                        
                                        deniz_aslan = false                                         # Bu kod sonuçta "Deniz 30 yaşındadır" dönecek
                                            print "Deniz 30 yaşındadır" unless deniz_aslan          # Çünkü print "Deniz 30 yaşındadır" , unless operatorunden sonra yanlış bir şey yazılırsa printi çalıştıracak
And &&
    * Bir boolean operatörüdür.                                                                    
    * && işareti ile gösterilir.                                                                    
    * Sadece iki yanındaki ifadelerin ikisi de doğru ise true olarak çalışır.
                                        boolean_2 = 2**3 == 8 && 3**2 == 9                          # Bu sorgu true dönecek çünkü && işaretinin her iki yanı da doğru
                                            puts boolean_2

                                        boolean_1 = 77 < 78 && 77 < 77                              # Bu sorgu false dönecek çünkü && işaretinin her iki yanı da doğru değil
                                            puts boolean_1

Or ||
    * Bir boolean operatörüdür
    * || işareti ile gösterilir
    * İki yandaki ifadelerden en az birisi doğru ise true olarak çalışır.
                                        boolean_1 = 2**3 != 3**2 || true                    
                                            puts boolean_1                                          # Bu sorgu true dönecek
                                        boolean_2 = false || -10 > -9
                                            puts boolean_2                                          # Bu sorgu false dönecek                                       
                                        boolean_3 = false || false
                                            puts boolean_3                                          # Bu sorgu false dönecek

Not !
    * Bir boolean operatörüdür
    * ! işareti ile gösterilir (methodların sonundaki ! ile karıştırılmamalı, bu başa yazılır)
    * true ları false, false ları true yapar
                                        boolean_1 = !true                    
                                            puts boolean_1                                          # Bu sorgu false dönecek                
                                        boolean_2 = !true && !true                    
                                            puts boolean_2                                          # Bu sorgu false dönecek           
                                        boolean_3 = !(700 / 10 == 70)                    
                                            puts boolean_3                                          # Bu sorgu false dönecek           

while
    * Loop yaratmak için kullanılır.
    * Kullanıcıdan istediğimiz türde bir cevap almamız için tekrarlar yaratır.
    * Eğer counter + 1 gibi bir artış kurmazsan bu infinite loop 'a sebebiyet verir. Çökmelerin önemli bir sebebidir.
                                        counter = 1
                                        while counter < 11                                          # Bu kod 1'den başlayarak 10'a kadar rakamları 1'er 1'er artırarak art arda yazacak
                                          puts counter
                                          counter = counter + 1
                                        end                

until
    * Loop yaratmak için kullanılır
    * Kullanıcıdan istediğimiz türde bir cevap almamız için tekrarlar yaratır.
    * Eğer counter + 1 gibi bir artış kurmazsan bu infinite loop 'a sebebiyet verir. Çökmelerin önemli bir sebebidir.
                                        counter = 1
                                        until counter > 11                                          # Bu kod 1'den başlayarak 11'a kadar rakamları 1'er 1'er artırarak art arda yazacak
                                          puts counter                                              # += işareti counter 'ı tekrar tekrar yazmak yerine getirilmiş bir şey, counter = counter +1 ile aynı şeyi yapıyor
                                          counter +=  1                                             # Bu kısayol her işlem türü için geçerli.
                                        end                                                         # Basitçe dilde karşılığı, "counter 'a 1 ekle ve bu yeni değeri counter olarak ata" demek

loop
    * Bir şeyi tekrarlamak için kullanılır
                                        counter = 0
                                        loop do
                                          counter += 1
                                          print "Ruby!"                                             # Bu komut "Ruby!" stringini 30 kere tekrarlayacak
                                          break if counter == 30                                    # Break kodunun üstündeki ifadeyi yazdırır
                                        end

for - in
    # Loop yaratmak için kullanılır
    # Kaç defa loop yapacağımızı bildiğimiz zamanlar kullanırız.
    # Bu kod Ruby'ye "1'den 10'a olan num değişkeni için, şunu yap:" diyor.
                                        for num in 1...10                                           # Bu kod bize 1'den 9'a kadar rakamları verecek. 10'u dışarda bırakacak.
                                        puts num                                                    # Bunun sebebi ... kullanmış olmamız. Eğer .. kullansaydık 10'a kadar gidecekti
                                        end                                                         # Aslında burada gizli bir print "#{num}" kodu gizli

do - end
    # {} işaretinin yaptığı şeyi yapar.
    # Loop yazımında kullanabilirsin. 
    # do , { olurken ; end , } olur.

Break
    # Looptan çıkış kartıdır.
    # Koşul sağlanırsa loopu bitirir.
                                        i = 20
                                        loop do
                                          i -= 1                                                    # Burada i değişkeni, 20'den geriye sayacak.
                                          print "#{i}"                                              # Break kullandığımız için 0'a küçük eşit olduğunda duracak
                                          break if i <= 0
                                        end

Next
    # Looptaki birkaç adımı atlamak için kullanılabilir.
    # Örneğin, çift rakamları yazdırmak istemiyorsak şöyle bir kod yazabiliriz:
                                        i = 20
                                        loop do
                                          i -= 1                                                    # Burada kod, 20'den 0'a kadar geriye saracak
                                          next if i % 2 == 1                                        # Eğer i değişkenini 2'ye böldüğünde kalan 1 ise next kodu sayesinde bu değerleri atlayacak.
                                          print "#{i}"                                              # Sonuçta bu kod bize sadece çift sayıları verecek
                                          break if i <= 0
                                        end
                                        
Array
    # Bir variable birden fazla değere bağlanmak istendiğinde kullanılır.
    # [ ] içine yazılan ve virgül ile ayrılan her şeydir. Array içindeki elementler aynı türden (string, boolean, interger vs.) olmalıdır.
                                        my_array = ["1", "turp", "5.0",]
    # Array içindeki her elementin bir indexi vardır. Array 'ın en sloundaki değer "index 0" olur. En sağdaki değer ise "index -1"
                                        üstteki örneği vermek gerekirse, array[1] bize "turp" elementini verir.
    # Array içinde array durumuna multidimensional array denir. Örneğin:
                                        multi_d_array = [[0,0,0,0],[9,8,7,4],[0,0,0,0],[0,0,0,0]]
    # Multidimensional Arraylar içinde index atmak basittir
                                        multi_d_array = [[0,0,0,0],[9,8,7,4],[0,0,0,0],[0,0,0,0]]  
                                        puts multi_d_array[1][2]                                    #Bu komut bize 7 sonucunu verecek     
                                    
Hash
    * Nasıl ki array 'da index yardımı ile ayırırız, hash içinde de key ile bu işi yaparız.
    * Aslında hash, içindeki elementleri (value) birer anahtara (key) bağlayarak bunları çağırmamıza yarar.
                                        my_hash = { "name" => "Eric",
                                          "age" => 26,
                                          "hungry?" => true                                         # Bu örnekte "name", "age" ve "hungry" birer key
                                        }                                                           # "Eric", 26 ve true ise birer value.   
                                                                                                    # Bir hash içinde farklı keylere bağlı string, boolean veya interger bulunabilir.  
                                        puts my_hash["name"]
                                        puts my_hash["age"]
                                        puts my_hash["hungry?"]
    * Hash.new koduna bir variable bağlayarak yeni bir hash yaratabiliriz.
    * Burada önemli nokta baştaki H harfinin büyük olmasıdır. Yoksa sistem neyden bahsettiğimizi anlamayacaktır.
                                        pets = Hash.new                                             # Bu kod adı pets olan içi boş bir hash yaratacak
    * Hash 'a value eklemenin iki yolu vardır.
                                        pets = Hash.new                                             # Bu kod pets hash 'ına Stevie key'i ve buna bağlı cat value 'sunu ekleyecek 
                                        pets["Stevie"] = "cat"                                      # Ardından puts komutu sayesinde cat yazdıracak
                                        puts pets["Stevie"]
                                    
Iterating over Arrays and Hashes
    * Iterator modlarını array ve hash için kullanma olayıdır.
                                        friends = ["Milhouse", "Ralph", "Nelson", "Otto"]

                                        family = { "Homer" => "dad",
                                        "Marge" => "mom",                                           # Bu kodda friends bir array iken family bir hash.
                                        "Lisa" => "sister",                                         # each iterator 'u, friends arrayındaki her değeri x olarak gördü (|x| sayesinde) ve puts etti
                                        "Maggie" => "sister",                                       # each iterator 'u, family hashindeki her degeri x ve y olarak gordu (|x, y|) ve yan yana puts etti
                                        "Abe" => "grandpa",                                         # Görüldüğü gibi array ve hash üzerine iterator mantığı burada biraz değişiyor
                                        "Santa's Little Helper" => "dog"
                                        }

                                        friends.each { |x| puts "#{x}" }
                                        family.each { |x, y| puts "#{x}: #{y}" }

                                        =end
    * Multidimensional Array 'lar içerisindeki değerleri teker teker yazdırmak istiyorsak izleyeceğimiz yol biraz daha farklı olacak:
                                            s = [["ham", "swiss"], ["turkey", "cheddar"], ["roast beef", "gruyere"]]

                                        s.each do |sub_array|
                                            sub_array.each do |another_sub_array|
                                                puts another_sub_array
                                            end
    * Burada tanımlı bir s array'ı var. İlk işlemimiz s array 'ını parçalara ayırmak oldu ve bu parçalara sub_array dedik
    * Artık sub_array tanımlı olduğu için, ikinci hedefimiz sub_array 'ı da parçalara ayırmak olmalı
    * Bunu da sub_array.each kodu ile yapıyoruz ve oluşan stringler 'e de another_sub_array diyoruz. Bunu yazdırınca da bütün parçalar birbirinden ayrışmış oluyor.
    * Hash 'ler üzerinde iteration yapmak ise daha farklı:
                                            secret_identities = {
                                                "The Batman" => "Bruce Wayne",
                                                "Superman" => "Clark Kent",                         # Bu kod, hash içindeki key ve value 'leri ikiye ayırdı (|hero, ego| kodu sayesinde)
                                                "Wonder Woman" => "Diana Prince",
                                                "Freakazoid" => "Dexter Douglas"
                                            }
  
                                            secret_identities.each do |hero, ego|
                                                puts "#{hero}: #{ego}"
                                            end
