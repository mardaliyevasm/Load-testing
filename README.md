# Load-testing
# Ingress Academy – Test Hesabatı

## 🔗 Sayt
[Ingress Academy](https://ingress.academy/en)

---

## ✅ Funksional Yoxlamalar

Sayta daxil oldum və aşağıdakı addımları yoxladım:

- "Apply Now" seçdim  
- Ad və soyad daxil etdim  
- "Training" bölməsinə keçdim  
- Kursların göründüyünü və seçim edilə bildiyini təsdiqlədim  

### Nəticə

- Əsas funksiyalar işləyir  
- Form submit mexanizmi aktivdir  
- Navigation düzgündür  
- Login → istifadəçi daxil olur  
- Submit → məlumat uğurla göndərilir  

---

## 🧪 Test Ssenariləri

### 1. Pozitiv Ssenarilər

- Saytı açdım → Ana səhifə uğurla yükləndi  
- “Training” bölməsinə klik etdim → Kurslar siyahısı açıldı  
- Kurs seçdim → Detail səhifə açıldı  
- “Apply” klik etdim → Müraciət formu açıldı  
- Formu düzgün doldurdum → Sistem qəbul etdi  
- Düzgün email daxil etdim → Error çıxmadı  
- “Submit” klik etdim → Məlumat göndərildi  
- Submitdən sonra → Success mesaj göstərildi  
- Səhifələr arasında keçid etdim → Navigation düzgün işlədi  
- Səhifəni yenilədim → Problem olmadı  

---

### 2. Negativ Ssenarilər

- Boş xanalarla submit → İcazə verilmədi  
- Email səhv formatda daxil edildi → Error mesaj çıxdı  
- Kurs seçilmədən submit → İcazə verilmədi  

---

## 🐞 Tapılan Buglar

### Bug 1: Dil dəyişdikdə əlaqə nömrəsi itir

**Addımlar:**
1. Saytı aç  
2. Hər hansı kurs səhifəsinə daxil ol  
3. Saytın dilini dəyiş (EN → AZ)  

**Gözlənilən nəticə:**  
- Əlaqə nömrəsi bütün dillərdə görünməlidir  

**Real nəticə:**  
- Dil dəyişdikdən sonra əlaqə nömrəsi yox olur  

---

### Bug 2: Dil dəyişdikdə “Təlimçilər” bölməsi yoxa çıxır

**Addımlar:**
1. Saytı aç  
2. Ana səhifədə “Təlimçilər” bölməsini tap  
3. Saytın dilini dəyiş  

**Gözlənilən nəticə:**  
- Bölmə bütün dillərdə görünməlidir  

**Real nəticə:**  
- Bölmə görünmür  

---

### Bug 3: “Haqqımızda” bölməsi tərcümə olunmur

**Addımlar:**
1. Saytı aç  
2. “Haqqımızda” bölməsinə daxil ol  
3. Saytın dilini dəyiş (AZ → EN)  

**Gözlənilən nəticə:**  
- Məzmun seçilmiş dilə uyğun dəyişməlidir  

**Real nəticə:**  
- Mətn tərcümə olunmur / eyni qalır  

---

## ⚙️ JMeter Load Test

### Nə etdim

- Saytın form submit və əsas səhifə yüklənməsi üzrə load test apardım  
- Müxtəlif istifadəçi sayları ilə test etdim:  
  - 10 user  
  - 50 user  
  - 100 user  

---

### Nəticələr

- **10 user** → Sistem stabil, cavab sürətli  
- **50 user** → Yüngül gecikmə müşahidə olunur  
- **100 user** →  
  - Bəzi request-lər gecikir  
  - Bəzən timeout baş verir  

---

## 📊 Ümumi Nəticə

- Yüksək yüklənmə zamanı performans zəifləyir  
- Response time artır  
- Bəzi hallarda server gec cavab verir  
