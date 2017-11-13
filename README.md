# Front-End Checklist

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Front-End Checklist**, web sitenizi/ HTML sayfanızı yayına vermeden önce test etmek için sahip olmanız gereken tüm öğelerin kapsamlı bir listesidir.

Bu, bazı diğer açık-kaynak kontrol listelerinden gelen eklemelerle birlikte Front-End geliştiricilerinin sahip olduğu yılların birikimine dayanır.

*Front-End Checklist' i Product Hunt üzerinden oylayarak ve önererek paylaşmaya yardımcı olun.*
[![](http://res.cloudinary.com/djnyaloac/image/upload/v1508896898/upvote-producthunt_vzys4c.jpg)](https://www.producthunt.com/posts/front-end-checklist)

## İçindekiler

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## Nasıl Kullanılır?

**Front-End Checklist**' de bulunan tüm öğeler web projelerinin çoğunluğu için gereklidir, fakat bazı öğeler dahil edilmeyebilir ya da birinci derecede önemli değildir(bir admin paneli web uygulamasında, örneğin RSS beslemesine gerek duymayabilirsiniz). Biz 3 esneklik seviyesi kullanmayı uygun buluyoruz:

* ![Low][low_img] öğenin tavsiye edildiği ama bazı özel durumlarda ihmal edilebileceğini ifade eder.
* ![Medium][medium_img] öğenin şiddetle tavsiye edildiğini ve ancak bazı çok önemli durumlarda çıkarılabileceğini ifade eder. Bazı öğeler dahil edilmediği taktirde performans ve SEO açısından istenmeyen sonuçlar doğurabilir.
* ![High][high_img] öğenin herhangi bir nedenden dolayı ihmal edilemeyeceğini ifade eder. Sayfanızda işlev bozukluğuna neden olabilir, erişilebilirlik veya SEO sorunlarıyla karşılaşabilirsiniz.

Bazı kaynaklar, içeriğin hangi tür olduğunu anlamanıza ya da kontrol listesi üzerinde bulabilmenize yardımcı olmak için bir ifadeye sahipler.

* 📖: belge veya makale
* 🛠: çevrimiçi araç / test aracı
* 📹: medya veya video içerik

---

## Head

> **Notlar:** HTML belgesinin `<head>` bölümünde bulunabilecek olan [her şeyin bir listesini](https://github.com/joshbuchea/HEAD) bulabilirsiniz.

### Meta etiketi

* [ ] **Doctype:** ![High][high_img] Doctype bir HTML5' tir ve tüm HTML sayfalarınızın en üst kısmındadır.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> * 📖 [Karakter kodlamasını belirleme - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*Sonraki 3 meta etiketinin (Charset, X-UA Compatible and Viewport) head alanında ilk olarak gelmesi gerekir.*

* [ ] **Charset:** ![High][high_img] Charset (UTF-8) doğru bir şekilde tanımlanır.

```html
<!-- Belge için karakter kodlamasını belirle -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Medium][medium_img] X-UA-Compatible meta etiketi mevcut.

```html
<!-- Internet Explorer' u  en yeni işleme motorunu kullanması için bilgilendir. -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> * 📖 [Eski belge durumlarını belirleme (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![High][high_img] Viewport doğru bir şekilde tanımlanır.

```html
<!-- Duyarlı web tasarım için Viewport -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![High][high_img] Tüm sayfalarda bir başlık kullanılır. (SEO: Google, başlıkta kullanılan karakterlerin piksel genişliğini, başlığı 472 ve 482 piksel arasında kesip ayırarak hesaplar. Ortalama karakter sınırı 55-karakter civarı olacaktır).

```html
<!-- Belge Başlığı -->
<title>Sayfa Başlığı 65 karakterden daha azdır.</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** ![High][high_img] Bir açıklama metası, eşsiz olan ve 150 karakterden fazlasına sahip olmayan bir şekilde oluşturulur.

```html
<!-- Meta Açıklama -->
<meta name="description" content="Sayfanın açıklaması 150 karakterden daha azdır.">
```

> * 📖[Meta Açıklama - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** ![Medium][medium_img] Her bir favicon doğru bir şekilde oluşturuldu ve görüntülendi. Eğer sadece bir `favicon.ico` ' nuna sahipseniz, onu sitenizin kök dizinine koyun. Normalde başka herhangi bir işaret kullanmanız gerekmez. Buna rağmen, aşağıdaki örneği kullanarak ona bağlantı vermek hala iyi bir uygulamadır. Günümüzde, `.ico` biçimine nazaran **PNG biçimi önerilir**.(boyutlar: 32x32px).

```html
<!-- Standart favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Önerilen favicon biçimi -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Oluşturucu](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Başvuru Kağıdı](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Hangisine ihtiyacınız var? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Low][low_img] Apple mobil web uygulamasına duyarlı Apple touch favicon mevcut.*(İhtiyacınız olabilecek tüm boyutları desteklemek için en azından 200x200px boyutlu Apple Icon dosyası oluşturun)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> * 📖 [Web Uygulamalarını Yapılandırma](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Low][low_img] Windows tiles mevcut ve bağlantı sağlanmış.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

browserconfig.xml dosyası için gereken minimum xml biçimlendirmesi aşağıdaki gibidir:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> * 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Medium][medium_img] Kopya içerikten kaçınmak için `rel="canonical"` kullanın.

```html
<!-- Kopya içerik sorunlarını önlemeye yardım eder -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

> * 📖 [Standart URL'ler kullanma- Search Console Yardım - Google Support](https://support.google.com/webmasters/answer/139066?hl=tr)
> * 📖 [rel=canonical ile ilgili 5 yaygın hata - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML etiketleri

* [ ] **Language attribute:** ![High][high_img] Web sitenizin `lang` özelliği belirtilmiş ve geçerli sayfanın diliyle ilişkilendirilmiştir.

```html
<html lang="en">
```

* [ ] **Direction attribute:** ![Medium][medium_img] Metin yönü HTML etiketi üzerinde belirtilmiş. (Bu farklı HTML etiketleri üzerinde kullanılabilir).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] Web sitenizin dil özelliği belirtilmiş ve geçerli sayfanın diliyle ilişkilendirilmiştir.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![Low][low_img] Gerek duyulması halinde, IE için koşullu yorumlar mevcuttur..

> * 📖 [Koşullu yorumlar hakkında (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low][low_img] Eğer projeniz bir blog ise veya makaleler içeriyorsa, bir RSS bağlantısı sağlandı.

* [ ] **inline critical CSS:** ![Medium][medium_img] Sayfa yüklenme ("ilk görünen üst kısım içeriği") sırasında hemen görünür olan içeriğe şekil veren CSS, kritik CSS olarak adlandırılır. Bu temel CSS kurallarınızdan önce ve tek bir satır olarak (küçültülmüş) `<style></style>` etiketleri arasına yerleştirilir.
> * 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical) bu işi otomatikleştirir

* [ ] **CSS order:** ![High][high_img] Tüm CSS dosyaları `<head>` alanında tüm JavaScript dosyalarından önce yüklenir. (Kimi zaman JS dosyalarının sayfanıza eşzamanlı olmayan bir şekilde yüklendileri durumlar dışında.)

### Sosyal meta

***Facebook OG*** and ***Twitter Cards***, herhangi bir web sitesi için şiddetle tavsiye edilir. Diğer sosyal medya etiketlerini de düşünebilirsiniz eğer onlar üzerinde özel bir varlığı hedefliyor veya görünümden emin olmak istiyorsanız.

* [ ] **Facebook Open Graph:** ![Low][low_img] Tüm Facebook Open Graph (OG) etiketleri test edilmiş ve hiçbiri eksik ya da yanlış bir bilgiye sahip değil. Resimlerin en az 600x315 piksel olması gerekir, 1200x600 piksel önerilir.

> **Notlar:** `og:image:width` and `og:image:height` kullanımı tarayıcı(Facebot) için resim boyutlarını belirtir ve böylece resmi eş zamanlı olmayan bir şekilde yüklemeye ve işlemeye gerek duymadan hemen sunabilir.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<!-- Sonraki etiketler isteğe bağlıdır ama önerilir -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [Web Yöneticileri İçin Paylaşım Rehberi](https://developers.facebook.com/docs/sharing/webmasters/)
> * 📖 [En İyi Uygulamalar - Paylaşma](https://developers.facebook.com/docs/sharing/best-practices/)
> * 🛠 [Facebook OG testing](https://developers.facebook.com/tools/debug/) ile sayfanızı test edin.

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Twitter cards başlangıç rehberi— Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 [Twitter card validator](https://cards-dev.twitter.com/validator) ile sayfanızı test edin.

**[⬆ başa dön](#table-of-contents)**

---

## HTML

### En iyi uygulamalar

* [ ] **HTML5 Anlamsal Öğeler:** ![High][high_img] HTML5 Anlamsal Öğeler gereğine uygun olarak kullanılıyor. (header, section, footer, main...).

> * 📖 [HTML Referans](http://htmlreference.io/)

* [ ] **Hata sayfaları:** ![High][high_img] Hata 404 ve 5xx sayfaları mevcut. 5xx hata sayfalarının CSS kurallarının dahili olması gerektiğini unutmayın(mevcut sunucu üzerinden hiçbir harici çağrı yok).

* [ ] **Noopener:** ![Medium][medium_img] `target="_blank"` 'e sahip harici bağlantılar kullanıyorsanız, sekme ele geçirme saldırısını önlemek için bağlantınızın bir `rel="noopener"` özelliğine sahip olması gerekir.

> * 📖 [rel=noopener hakkında](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Yorumları temizle:** ![Low][low_img] Gereksiz kodlar sayfa yayına verilmeden önce kaldırılmalıdır.

### HTML testi

* [ ] **W3C uyumlu:** ![High][high_img] Muhtemel HTML kod sorunlarını belirlemek için tüm sayfalar W3C doğrulayıcıyla test edilmelidir.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] HTML kodumda karşılaşabileceğim herhangi bir sorunu analiz etmeme yardım edecek araçlar kullanırım.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)
> * 🛠 [Sonar a linting tool for the web](https://sonarwhal.com/)

* [ ] **Bağlantı kontrolcüsü:** ![High][high_img] Sayfamda hiç kırık bağlantı yok, 404 hatanız olmadığını doğrulayın.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Reklam engelleyici testi:** ![Medium][medium_img] Web siteniz, reklam engelleyici yazılımların aktif olduğu durumda, içeriğinizi doğru şekilde gösteriyor.(İnsanlara reklam engelleyici yazılımlarını devre dışı bırakmalarını teşvik edici bildirimler sunabilirsiniz).



**[⬆ başa dön](#table-of-contents)**

---

## Webfonts

> **Notlar:** Web yazı tipleri kullanmak, biçimlendirilmemiş metin ortaya çıkması(FOUT)/ net görünmeyen metin belirmesi(FOIT) sorunlarına neden olabilir. Bu durumu kontrol etmek için alternatif yazı tipleri ve/veya web yazı tipi yükleyicilerini kullanmayı düşünün.
> * 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

* [ ] **Web yazı tipi dosya biçimi:** ![High][high_img] WOFF, WOFF2 ve TTF tüm modern tarayıcılarla desteklenir.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Web yazı tipi boyutu:** ![High][high_img] Web yazı tipi dosyaları 2 MB(tüm biçimler dahil) 'ı aşmamalı.

* [ ] **Web yazı tipi yükleyicisi:** ![Low][low_img] Bir web yazı tipi yükleyicisi ile yükleme davranışını kontrol edin.

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ başa dön](#table-of-contents)**

---

## CSS

> **Notlar:** Pek çok Front-End geliştiriciler tarafından takip edilen [CSS Kılavuz](https://cssguidelin.es/) ve [Sass Kılavuz](https://sass-guidelin.es/) sitelerine gözatın. Eğer CSS özellikleri ile ilgili şüphelerin varsa, [CSS Reference](http://cssreference.io/) sitesini ziyaret edebilirsin.

* [ ] **Duyarlı Web Tasarım:** ![High][high_img] Web site, duyarlı web tasarımı uyguluyor. 
* [ ] **CSS Print:** ![Medium][medium_img] Bir baskı stil dosyası sağlanmış ve her sayfada hatasız.
* [ ] **Önişlemciler:** ![Low][low_img] Sayfanız bir CSS önişlemcisi kullanıyor ([Sass](http://sass-lang.com/) tercih edilen).
* [ ] **Benzersiz Kimlik:** ![High][high_img] Eğer kimlik kullanılıyorsa, her sayfa için benzersizdir.
* [ ] **CSS Sıfırlama:** ![High][high_img] CSS sıfırlama işlemi( sıfırlama, standartlaştırma veya yeniden yükleme) kullanıldı ve güncel. *(Eğer Bootstrap veya Foundation gibi CSS Framework' ları kullanıyorsanız zaten bu işlemler dahil edilmiştir.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS öneki:** ![Low][low_img] JavaScript dosyalarında kullanılan tüm class ve id' ler **js-** ile başlıyor ve CSS dosyalarında stilize edilmemiş.

```html
<div id="js-slider" class="my-slider">
<!-- Veya -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Gömülmüş veya satır içi CSS:** ![High][high_img] CSS işlemlerinizi `<style>` etiketlerine gömmekten veya satır için CSS kullanmaktan mümkün mertebe kaçının: sadece geçerli  sebebler için kullanın (slider için background-image, kritik CSS gibi).
* [ ] **Sağlayıcı önekleri:** ![High][high_img] Css sağlayıcı önekleri kullanıldı ve tarayıcınızın uyumluluk desteğine göre oluşturuldu.

> * 🛠 [Çevrimiçi Autoprefixer CSS](https://autoprefixer.github.io/)

### Performance

- [ ] **Concatenation:** ![High][high_img] CSS files are concatenated in a single file. *(Not for HTTP/2)*
- [ ] **Minification:** ![High][high_img] All CSS files are minified.
- [ ] **Non-blocking:** ![Medium][medium_img] CSS files need to be non-blocking to prevent the DOM from taking time to load.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Low][low_img] Remove unused CSS.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS testing

* [ ] **Stylelint:** ![High][high_img] All CSS or SCSS files are without any errors.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High][high_img] All pages were tested at the following breakpoints: 320px, 768px, 1024px (can be more / different according to your analytics).

* [ ] **CSS Validator:** ![Medium][medium_img] The CSS was tested and pertinent errors were corrected.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers:** ![High][high_img] All pages were tested on all current desktop browsers (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Mobile Browsers:**  ![High][high_img] All pages were tested on all current mobile browsers (Native browser, Chrome, Safari...).
* [ ] **OS:**  ![High][high_img] All pages were tested on all current OS (Windows, Android, iOS, Mac...).

- [ ] **Pixel perfect:** ![High][high_img] Pages are close to pixel perfect. Depending on the quality of the creatives, you may not be 100% accurate, but your page needs to be close to your template.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction:** ![High][high_img] All pages need to be tested for LTR and RTL languages if they need to be supported.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## Images

> **Notes:** For a complete understanding of image optimization, check the free ebook **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### Best practices

* [ ] **Optimization:** ![High][high_img] All images are optimized to be rendered in the browser. WebP format could be used for critical pages (like Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Picture/Srcset:** ![Medium][medium_img] You use picture/srcset to provide the most appropriate image for the current viewport of the user.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** ![Low][low_img] You provide layout images 2x or 3x, support retina display.
* [ ] **Sprite:** ![Medium][medium_img] Small images are in a sprite file (in the case of icons, they can be in an SVG sprite image).
* [ ] **Width and Height:** ![High][high_img] Set `width` and `height` attributes on `<img>` if the final rendered image size is known (can be omitted for CSS sizing).
* [ ] **Alternative text:** ![High][high_img] All `<img>` have an alternative text which describe the image visually.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** ![Medium][medium_img] Images are lazyloaded (A noscript fallback is always provided).

**[⬆ back to top](#table-of-contents)**

---

## JavaScript

### Best practices

* [ ] **JavaScript Inline:** ![High][high_img] You don't have any JavaScript code inline (mixed with your HTML code).
* [ ] **Concatenation:** ![High][high_img] JavaScript files are concatenated.
* [ ] **Minification:** ![High][high_img] JavaScript files are minified (you can add the `.min` suffix).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **Non-blocking:** ![Medium][medium_img] JavaScript files are loaded asynchronously using `async` or deferred using `defer` attribute.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] If you need to target some specific features you can use a custom Modernizr to add classes in your `<html>` tag.

> * 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![High][high_img] No errors are flagged by ESLint (based on your configuration or standards rules).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### Scan and check your web site

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Best practices

* [ ] **HTTPS:** ![Medium][medium_img] HTTPS is used on every pages and for all external content (plugins, images...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] The HTTP header is set to 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] You ensure that requests made to your server-side are legitimate and originate from your website / app to prevent CSRF attacks.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] Your page or website is free from XSS possible issues.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] Prevents Google Chrome and Internet Explorer from trying to mime-sniff the content-type of a response away from the one being declared by the server.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] Protects your visitors against clickjacking attacks.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### Best practices

- [ ] **Weight page:** ![High][high_img] The weight of each page is between 0 and 500 KB.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium][medium_img] Your HTML is minified.
> * 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Medium][medium_img] Images, scripts and CSS need to be lazy loaded to improve the response time of the current page (See details in their respective sections).

* [ ] **Cookie size:** If you are using cookies be sure each cookie doesn't exceed 4096 bytes and your domain name doesn't have more than 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Third party components:** ![Medium][medium_img] Third party iframes or components relying on external JS (like sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping your users activity private.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] DNS of third-party services that may be needed are resolved in advance during idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Low][low_img] DNS lookup, TCP handshake and TLS negociation with services that will be needed soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Low][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`) in advance using `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![High][high_img] All your pages were tested (not only the homepage) and have a score of at least 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **Notes:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Medium][medium_img] Major functionality like main navigation and search should work without JavaScript enabled.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![High][high_img] Headings should be used properly in the right order (H1 to H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>` has `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` has `role="navigation"`.
- [ ] **Role main:** ![High][high_img] `<main>` has `role="main"`.

> * 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semantics

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] This is especially important for mobile devices that show customized keypads and widgets for different types.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![High][high_img] A label is associated with each input form element. In case a label can't be displayed, use `aria-label` instead.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing

* [ ] **Accessibility standards testing:** ![High][high_img] Use the WAVE tool to test if your page respects the accessibility standards.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Medium][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![High][high_img] If the focus is disabled, it is replaced by visible state in CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] Google Analytics is installed and correctly configured.
* [ ] **Headings logic:** ![Medium][medium_img] Heading text helps to understand the content in the current page.
* [ ] **sitemap.xml:** ![High][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously Google Webmaster Tools).
* [ ] **robots.txt:** ![High][high_img] The robots.txt is not blocking webpages.

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] Pages using structured data are tested and are without errors. Structured data helps crawlers understand the content in the current page.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Heirarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Medium][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of your website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ back to top](#table-of-contents)**

---

## Translation

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)

---

## Front-End Checklist Badge

If you want to show you are following the rules of the Front-End Checklist, put this badge on your README file!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](http://frontendchecklist.com/) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

### Contributors

Check out all the super awesome [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Support

If you have any question or suggestion, don't hesitate to use Gitter or Twitter:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Facebook](https://www.facebook.com/frontendchecklist/)
* [Twitter](https://twitter.com/thedaviddias)

## Authors

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
