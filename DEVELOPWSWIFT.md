<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ziya Kök - Developing with Swift</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #e9ecef;
            color: #343a40;
        }
        header {
            background: #007bff;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        header h1 {
            margin: 0;
            font-size: 2.5em;
        }
        header p {
            margin: 5px 0 0;
            font-size: 1.1em;
        }
        nav {
            display: flex;
            justify-content: center;
            gap: 20px;
            padding: 10px 0;
            background: #fff;
            border-bottom: 1px solid #dee2e6;
        }
        nav a {
            color: #007bff;
            text-decoration: none;
            font-weight: bold;
            padding: 10px 20px;
            border-radius: 5px;
            transition: background-color 0.3s, color 0.3s;
        }
        nav a:hover {
            background-color: #007bff;
            color: #fff;
        }
        main {
            padding: 20px;
            max-width: 900px;
            margin: 20px auto;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h2 {
            color: #007bff;
            border-bottom: 2px solid #007bff;
            padding-bottom: 5px;
            margin-bottom: 15px;
        }
        p {
            line-height: 1.6;
        }
        footer {
            text-align: center;
            padding: 20px;
            background: #007bff;
            color: #fff;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Ziya Kök - Developing with Swift</h1>
        <p>Home / CS-50 Course / Documentation / Projects</p>
    </header>
    <nav>
        <a href="https://ziyarko.github.io/CS-50COURSE.html">CS-50 Course</a>
        <a href="https://ziyarko.github.io/DOCUMENTATION.html">Documentation</a>
        <a href="https://ziyarko.github.io/PROJECTS.html">Projects</a>
        <a href="https://ziyarko.github.io">Home</a>
    </nav>
    <main>
        <h2>Introduction</h2>
        <p>Hello! 👋 My name is Ziya, and this is my page for Developing with Swift.</p>
    <h2>Why Swift?</h2>
        <p>Swift is a powerful and intuitive programming language developed by Apple. I chose Swift because it makes it easier to build fast, reliable, and safe software for iOS, macOS, watchOS, and tvOS.</p>
    <h2>Learning Resources</h2>
        <p>Here are some of the resources I used to learn Swift:</p>
        <ul>
            <li>Apple's Swift documentation</li>
            <li>Developing iOS Apps with Swift by Stanford University</li>
            <li>Various tutorials on Swift Playgrounds</li>
        </ul>
    </main>

<footer>
        <p>&copy; 2024 Ziya Kök. All rights reserved.</p>
    </footer>
  <section>
        <h2>Projects made with Swift 1-17:</h2>
        <a href="https://github.com/Ziyarko/ziyarkodevelopswift.github.io">Swift Code</a>
        <a href="https://github.com/Ziyarko/Xcode-Projects">X-Code projects 2</a>

   <h2>Apps:</h2>
        <a href="https://github.com/Ziyarko/ziyarkodevelopswift.github.io">Phototframe/a>
        <a href="https://github.com/Ziyarko/Photoframe">BouncyBall App</a>
        <a href="https://github.com/Ziyarko/QuestionBot">Questionbot App</a>
       <a href="https://github.com/Ziyarko/ziyarkodevelopswift.github.io/tree/main/MemeMakerReal">MemeMaker</a> 
       <a href="https://github.com/Ziyarko/ziyarkodevelopswift.github.io/tree/main/RockPaperScissors%20Final">RockPaperScissors</a> 
       <a href=" https://github.com/Ziyarko/ziyarkodevelopswift.github.io/tree/main/ColourPicker">RockPaperScissors</a> 
           
        
 


 <h2>Swift Ui Projects:</h2>
      <a href=" https://github.com/Ziyarko/SwiftUi-Landmark/tree/main/SwiftUi%20Landmark.xcodeproj">Swift Uİ Landmark,</a> 
      <a href=" https://github.com/Ziyarko/MySelfIn6Words">Myself In Six Words,</a> 
      <a href=" https://github.com/Ziyarko/HelloSwiftUiReal/tree/main/Calculator">CalculatorSwiftUi,</a> 
      <a href=" https://github.com/Ziyarko/HelloSwiftUiReal/tree/main/HelloSwiftUiReal">HelloSwiftUi,</a> 
    <a href=" https://youtu.be/T5In3RVzqYI">(Playground)Rock paper scissors Documentation</a> 
  
    
    
 <h2>Ap csp portofolio</h2>
<a href="https://youtu.be/qXw-Z93R-FQ">Ap Csp Portofolio program video </a> 

 <h2>Ap csp code</h2>
        <p>
// Portions of the code (such as functions, logic, or debugging support) were co-written with the assistance of generative AI tools like ChatGPT. 

import SwiftUI

struct ContentView: View {
    @State private var numberToGuess = Int.random(in: 1...100)
    @State private var userGuess: String = ""
    @State private var userGuessReal: Int = 0
    @State private var attemptCount = 0
    @State private var feedback = ""
    @State private var pastGuesses: [Int] = []
    @State private var sumOfPastGuesses: Int = 0
    
 var body: some View {
        VStack(spacing: 25) {
            HStack(alignment: .top) {
                VStack(alignment: .leading, spacing: 5) {
                    Text("Past Guesses:")
                        .font(.headline)
                                 ForEach(pastGuesses.prefix(10).reversed(), id: \.self) { guess in
                        Text("\(guess)")
                            .font(.body)
                    }
                               Spacer()
                }
                .padding(.leading)
                       VStack(spacing: 20) {
                    Text("Number Guessing Game")
                        .font(.largeTitle)
                        .bold()
                            Text("Guess a number between 1 and 100")
                        .font(.title3)
                                 Text("Attempts: \(attemptCount)")
                        .font(.title3)
                        TextField("Enter your guess", text: $userGuess)
                        .keyboardType(.numberPad)
                        .padding()
                        .background(Color.gray)
                        .cornerRadius(5)
                        .overlay(RoundedRectangle(cornerRadius: 5).stroke(Color.gray, lineWidth: 1))
                        .frame(width: 200)
                           Button("Submit Guess") {
                        checkGuess()
                    }
                    .padding(.horizontal, 20)
                    .padding(.vertical, 10)
                    .background(Color.blue)
                    .foregroundColor(.white)
                    .cornerRadius(10)
                          Text(feedback)
                        .font(.headline)
                        .foregroundColor(.purple)
                        .padding()
                        .background(Color(.systemGray6))
                        .cornerRadius(10)
                    
 Button("Fun Fact: Find the Sum of Past 10 Guesses") {
                        sumOfPastGuesses = calculateSumOfPastGuesses(from: pastGuesses)
                    }
                    .padding()
                    .background(Color.green)
                    .foregroundColor(.white)
                    .cornerRadius(10)
          Text("Sum of Past 10 Guesses: \(sumOfPastGuesses)")
                        .font(.title2)
                        .foregroundColor(.blue)
                }
                .padding(.trailing)
            }
            .padding(.top)
        }
    }   
    func checkGuess() {
        if let guess = Int(userGuess) {
            userGuessReal = guess
        } else {
            feedback = "Please enter a valid integer!"
            return
        }
        if userGuessReal < 0 || userGuessReal > 100 {
            feedback = "Please enter a valid integer!"
            return
        }
        pastGuesses.append(userGuessReal)
        if pastGuesses.count > 10 {
            pastGuesses.removeFirst()
        }
        
  attemptCount += 1
        
if userGuessReal < numberToGuess {
            feedback = "Too low! Try again."
        } else if userGuessReal > numberToGuess {
            feedback = "Too high! Try again."
        } else {
            feedback = "🎉 Correct! You guessed it in \(attemptCount) tries."
            numberToGuess = Int.random(in: 1...100)
            attemptCount = 0
        }
             userGuess = ""
    }
    
func calculateSumOfPastGuesses(from pastGuesses: [Int]) -> Int {
        var sum = 0
        let lastGuesses = pastGuesses.prefix(10)
        for i in lastGuesses {
            sum += i
        }
        return sum
    }
}
</p>
 <h2>Ap Csp portofolio questions</h2>
        <p>Program Amaç ve İşlevi (Program Purpose and Function)
Programınızın amacı nedir?
Kullanıcının karbon ayak izini hesaplamak.

Hangi problemi çözmeyi hedefliyor?
Çevresel farkındalık eksikliğini azaltmak.

Programınız kullanıcılara ne sağlar?
Kendi karbon salınımlarını görüp azaltma yolları sunar.

Programın temel işlevleri nelerdir?
Veri girişi, hesaplama, sonuç gösterimi ve öneri sunma.

Kullanıcı bu programı nasıl kullanır?
Ulaşım, enerji, diyet gibi bilgileri girer, sonuçları görür.

Program Geliştirme Süreci (Program Development Process)
Bu program fikrine nasıl ulaştınız?
Sürdürülebilirlik ve çevre konularına ilgim vardı.

Programı geliştirirken nasıl bir planlama yaptınız?
Ekranları ve veri girişlerini tasarlayıp sırayla kodladım.

Geliştirme sürecinde kimden geri bildirim aldınız?
Öğretmenim ve arkadaşlarımdan.

Bu geri bildirimler doğrultusunda ne gibi değişiklikler yaptınız?
Arayüzü sadeleştirdim ve öneri sistemini ekledim.

Programınızı test ederken nasıl bir yöntem kullandınız?
Farklı veri kombinasyonları ile deneme yaptım.

Algoritma Açıklaması (Algorithm Implementation)
Programınızda hangi algoritmayı kullanıyorsunuz?
Giriş verilerine göre puan hesaplama algoritması.

Bu algoritma nasıl çalışıyor (adım adım açıklayınız)?

Kullanıcı verileri girer.

Her kategoriye puan verilir.

Toplam puan hesaplanır.

Sonuç ve öneri gösterilir.

Bu algoritmanın içinde koşul (if), döngü (loop) ve işlev (procedure) nasıl kullanılıyor?
if ile seçeneklere göre puan veriliyor,
bazı kısımlarda öneri listesi için loop,
hesaplama için function kullanıldı.

Bu algoritma programın hangi bölümünde önemli rol oynuyor?
Sonuç hesaplama ve öneri sunma kısmında.

Soyutlama Kullanımı (Abstraction)
Programınızda bir işlev (function/method) tanımladınız mı?
Evet.

Bu işlev ne işe yarıyor?
Karbon puanını hesaplıyor.

Hangi tekrar eden görevleri soyutlayarak daha sade kod elde ettiniz?
Her kategoriye puan verme işlemini.

Bu soyutlama, kodun okunabilirliğini nasıl artırdı?
Kod daha kısa, düzenli ve anlaşılır hale geldi.

Etki ve Geri Bildirim (Impact and Reflection)
Programınızın sosyal, etik veya ekonomik bir etkisi olabilir mi?
Evet, çevresel farkındalığı artırabilir.

Kullanıcılar program hakkında size ne tür geri bildirim verdi?
Basit ve bilgilendirici olduğunu söylediler.

Programınızın sınırlılıkları nelerdir?
Veriler kullanıcı tahminine dayalı, çok detaylı değil.

Gelecekte programınızı nasıl geliştirmeyi düşünüyorsunuz?
Gerçek veri entegrasyonu ve grafiklerle gelişmiş sonuçlar.

Hatalar ve Çözümler (Debugging and Problem Solving)
Kodunuzu yazarken hangi hatalarla karşılaştınız?
Yanlış girişlerde uygulama çökmesi gibi.

Bu hatalar ne zaman ve nasıl ortaya çıktı?
Test sırasında yanlış veri girince fark ettim.

Hataları tespit etmek için ne yaptınız?
print komutları ve Xcode hata mesajlarını kullandım.

Hatanın kaynağını nasıl belirlediniz?
Kod akışını adım adım inceledim.

Hataları çözmek için denediğiniz yöntemler nelerdir?
Koşullar ve veri tipi kontrolleri ekledim.

Bu süreçte araştırma yapmanız gerekti mi? Hangi kaynaklardan faydalandınız?
Evet, Stack Overflow ve Apple SwiftUI dokümantasyonu.

Bu hatalardan ne öğrendiniz?
Kullanıcı hatalarına karşı önlem almanın önemli olduğunu.

İstersen bu cevapları GitHub'a uygun şekilde Markdown formatında da düzenleyebilirim.







You said:
biraz daha uzun cevaplar yaz


ChatGPT said:
Elbette! İşte AP Computer Science Principles – GitHub Documentation Soruları için her soruya orta uzunlukta, açık ama sade cevaplar:

📌 Program Amaç ve İşlevi (Program Purpose and Function)
Programınızın amacı nedir?
Bu programın amacı, kullanıcıların günlük yaşam alışkanlıklarına göre kişisel karbon ayak izlerini hesaplayarak çevresel etkilerini görmelerini sağlamaktır.

Hangi problemi çözmeyi hedefliyor?
Birçok insan kendi çevresel etkilerinin farkında değil. Bu program, bu farkındalığı artırmayı ve sürdürülebilir yaşam konusunda bilinç kazandırmayı hedefliyor.

Programınız kullanıcılara ne sağlar?
Kullanıcılar, ulaşım, enerji kullanımı, beslenme ve atık alışkanlıklarına göre karbon ayak izlerini görebilir ve çevreye daha az zarar vermek için öneriler alabilirler.

Programın temel işlevleri nelerdir?
Kullanıcılardan veri toplar, bu verileri analiz eder, bir karbon puanı hesaplar ve kullanıcılara bu sonuca göre kişiselleştirilmiş öneriler sunar.

Kullanıcı bu programı nasıl kullanır?
Kullanıcı belirli sorulara cevap vererek ulaşım tercihini, enerji kullanımını, diyet türünü ve geri dönüşüm alışkanlıklarını girer. Ardından sonuçları ve önerileri görür.

🧠 Program Geliştirme Süreci (Program Development Process)
Bu program fikrine nasıl ulaştınız?
Çevre kirliliği ve iklim değişikliğiyle ilgili haberlerden etkilenerek insanların bireysel etkilerini fark etmelerine yardımcı olacak bir araç geliştirmek istedim.

Programı geliştirirken nasıl bir planlama yaptınız?
İlk olarak hangi verilerin alınacağını ve nasıl bir skor sistemiyle değerlendirileceğini planladım. Ardından kullanıcı arayüzünü tasarladım ve her adımı sırayla kodladım.

Geliştirme sürecinde kimden geri bildirim aldınız?
Öğretmenimden ve birkaç arkadaşım ile aile bireylerinden geri bildirim aldım. Uygulamayı test etmelerini istedim.

Bu geri bildirimler doğrultusunda ne gibi değişiklikler yaptınız?
Arayüzü daha sade ve anlaşılır hale getirdim. Ayrıca öneri bölümünü rastgele değil, daha mantıklı eşleştirmelerle sunacak şekilde geliştirdim.

Programınızı test ederken nasıl bir yöntem kullandınız?
Farklı veri kombinasyonlarını deneyerek sistemin doğru hesaplama yapıp yapmadığını kontrol ettim. Ayrıca geçersiz girişlere karşı hata kontrolü ekledim.

⚙️ Algoritma Açıklaması (Algorithm Implementation)
Programınızda hangi algoritmayı kullanıyorsunuz?
Karbon ayak izini hesaplamak için her kategoriye bir puan sistemi uygulayan bir algoritma kullanıyorum.

Bu algoritma nasıl çalışıyor (adım adım açıklayınız)?

Kullanıcı her kategori için bir seçim yapar.

Her seçimin arkasında belirli bir karbon puanı vardır.

Bu puanlar toplanarak toplam karbon ayak izi hesaplanır.

Sonuç kullanıcıya gösterilir ve uygun öneriler sunulur.

Bu algoritmanın içinde koşul (if), döngü (loop) ve işlev (procedure) nasıl kullanılıyor?
if ifadeleriyle hangi seçimin hangi puanı alacağı belirleniyor.
Bazı işlemler için for döngüsü kullanılıyor (örneğin öneri seçimi).
Hesaplama işlemi ve öneri sunumu için function tanımlandı.

Bu algoritma programın hangi bölümünde önemli rol oynuyor?
Bu algoritma, kullanıcının sonuçlarını ve önerilerini belirleyen temel sistem olduğu için programın en önemli parçasıdır.

🧩 Soyutlama Kullanımı (Abstraction)
Programınızda bir işlev (function/method) tanımladınız mı?
Evet, karbon hesaplamasını yapan ve öneri sunan işlevler tanımladım.

Bu işlev ne işe yarıyor?
Girilen verilere göre karbon skorunu hesaplıyor ve kullanıcıya özel öneriler oluşturuyor.

Hangi tekrar eden görevleri soyutlayarak daha sade kod elde ettiniz?
Kategori başına puan hesaplama işlemleri tekrar ettiği için her biri fonksiyon haline getirildi.

Bu soyutlama, kodun okunabilirliğini nasıl artırdı?
Kod daha düzenli, okunabilir ve değişiklik yapmaya daha uygun hale geldi.

🌍 Etki ve Geri Bildirim (Impact and Reflection)
Programınızın sosyal, etik veya ekonomik bir etkisi olabilir mi?
Evet. Bu program, kullanıcıların çevreye verdikleri zararı fark edip daha bilinçli tercihler yapmalarına katkı sağlayabilir.

Kullanıcılar program hakkında size ne tür geri bildirim verdi?
Basit, kullanışlı ve bilgilendirici olduğunu söylediler. Önerilerin ilham verici olduğu yorumunu da aldım.

Programınızın sınırlılıkları nelerdir?
Veriler kullanıcı beyanına dayalı olduğu için kesin sonuçlar veremez. Ayrıca her ülkeye özel emisyon faktörleri kullanılmıyor.

Gelecekte programınızı nasıl geliştirmeyi düşünüyorsunuz?
Gerçek verilerle karşılaştırma, grafik gösterimi ve daha detaylı analiz özellikleri eklemeyi planlıyorum.

🐞 Hatalar ve Çözümler (Debugging and Problem Solving)
Kodunuzu yazarken hangi hatalarla karşılaştınız?
Kullanıcının sayı yerine harf girmesi uygulamanın çökmesine neden oldu. Ayrıca bazı puanlar yanlış hesaplanıyordu.

Bu hatalar ne zaman ve nasıl ortaya çıktı?
Test aşamasında veri girerken ve farklı senaryoları denerken fark ettim.

Hataları tespit etmek için ne yaptınız?
print() komutlarıyla verileri kontrol ettim, Xcode hata mesajlarını dikkatle inceledim.

Hatanın kaynağını nasıl belirlediniz?
Kod akışını adım adım kontrol ederek hatanın hangi noktada ortaya çıktığını tespit ettim.

Hataları çözmek için denediğiniz yöntemler nelerdir?
Koşul kontrolleri, veri tipi doğrulaması ve daha net kullanıcı uyarıları ekledim.

Bu süreçte araştırma yapmanız gerekti mi? Hangi kaynaklardan faydalandınız?
Evet, SwiftUI belgeleri, Stack Overflow ve Apple geliştirici forumlarından yararlandım.

Bu hatalardan ne öğrendiniz?
Kullanıcı etkileşimini hesaba katarak daha sağlam ve esnek kod yazmanın önemini fark ettim</p>
 
 
          
       
<h2>Apps:</h2>
        
        
      
        
</section>
</body>
</html>




yavuz selvili özbaş
