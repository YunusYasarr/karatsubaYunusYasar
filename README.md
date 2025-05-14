# Karatsuba Algoritması

Karatsuba algoritması, büyük sayıların çarpılmasını hızlandıran bir algoritmadır. Klasik çarpma yönteminin `O(n^2)` zaman karmaşıklığına karşılık, Karatsuba algoritması daha verimli bir çözüm sunarak `O(n^1.585)` zaman karmaşıklığı sağlar.

## İçerik

- [Algoritmanın Açıklaması](#algoritmanın-açıklaması)
- [Kullanım Alanları](#kullanım-alanları)    
- [Avantajlar ve Dezavantajlar](#avantajlar-ve-dezavantajlar)
- [Zaman ve Uzay Karmaşıklığı](#zaman-ve-uzay-karmaşıklığı)
- [Nasıl Kullanılır?](#nasıl-kullanılır)
- [Test Dosyası](#test-dosyası)

---

## Algoritmanın Açıklaması

Karatsuba algoritması, çok büyük sayıların çarpılmasında klasik yöntemden daha hızlı sonuç verir. Algoritma, sayıları ikiye bölerek 3 adet küçük çarpma işlemi yapar ve ardından bu çarpımlar ile sonucu birleştirir.

### Adımlar:

1. **Sayının ikiye bölünmesi**:
   - Verilen sayılar `x` ve `y` ikiye ayrılır: `x = a * 10^m + b`, `y = c * 10^m + d`
   
2. **3 küçük çarpma yapılır**:
   - `ac`, `bd` ve `(a + b)(c + d)` hesaplanır.
   
3. **Ara çarpım**:
   - `ad + bc`, `(a + b)(c + d) - ac - bd` işlemi ile bulunur.

4. **Sonuç birleştirilir**:
   - `x * y = ac * 10^(2m) + (ad + bc) * 10^m + bd`

5. **Rekürsif olarak daha küçük sayı çarpımları yapılır**.

---

## Kullanım Alanları

Karatsuba algoritması, genellikle **çok büyük sayıların çarpılması gereken** durumlarda kullanılır. Başlıca kullanım alanları şunlardır:

1. **Kriptografi**: RSA, Diffie-Hellman gibi şifreleme algoritmalarında büyük asal sayıların çarpımı.
2. **Büyük Sayı Aritmetiği**: Python, Java gibi dillerde kullanılan `BigInteger` sınıflarındaki hesaplamalar.
3. **Bilimsel Hesaplamalar**: Büyük sayıların hassas hesaplandığı astrofizik, biyoloji ve genetik hesaplamalar.
4. **Matematiksel Yazılımlar**: Mathematica, MATLAB gibi yazılımlarda büyük sayılarla yapılan işlemler.

---

## Avantajlar ve Dezavantajlar

### Avantajlar:
- **Daha Hızlı Çarpma**: Klasik çarpma `O(n^2)` iken Karatsuba `O(n^1.585)` zaman karmaşıklığına sahiptir.
- **Daha Az Çarpma**: 4 yerine sadece 3 çarpma işlemi yapılır.
- **Paralel İşlemeye Uygun**: Rekürsif yapısı, paralel işleme ile hızlandırılabilir.
- **Eğitimsel Değer**: Böl ve fethet stratejisine güzel bir örnek.

### Dezavantajlar:
- **Küçük Sayılar İçin Verimsiz**: Küçük sayılarda klasik yöntem daha hızlıdır.
- **Daha Fazla Toplama/Çıkarma**: Daha fazla toplama ve çıkarma işlemi yapılır.
- **Karmaşıklık**: Uygulaması ve anlaşılması daha karmaşıktır.
- **Bellek Kullanımı**: Rekürsif yapısı nedeniyle daha fazla bellek kullanımı gerektirir.

---

## Zaman ve Uzay Karmaşıklığı

### Zaman Karmaşıklığı:
- Karatsuba algoritması `O(n^1.585)` zaman karmaşıklığına sahiptir.
- Klasik çarpma yöntemi ise `O(n^2)` zaman alır.
  
### Uzay Karmaşıklığı:
- Karatsuba algoritması `O(n)` uzay karmaşıklığına sahiptir.
- Rekürsif çağrılar ve ara veriler için ek bellek kullanımı gerektirir.

---

## Nasıl Kullanılır?

### Derleme ve Çalıştırma

1. `karatsuba.cpp` dosyasındaki Karatsuba fonksiyonunun bulunduğundan emin olun.
2. `test.cpp` dosyasını oluşturun ve şu komutla derleyin:

```bash
g++ test.cpp karatsuba.cpp -o test
./test
```