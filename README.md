# Facebook-Otomatik-Takipten-Cikma

### ADIM 1

<p>- Facebook dilini Türkçe yap</p>
<p>- Tampermonkey eklentisi tarayıcınıza ekleyin</p>
<p>- Yeni Betik oluştura tıklayın</p>

![image](https://github.com/DenizKod/ARK-ISTEGI-IPTAL-ETME/assets/168285638/7e1b2696-803e-447a-ae3f-f7844a44d28f)

#### Aşağıdaki kodu betik oluşturma sayfasına yapıştırıp betiği kaydedin

```
// ==UserScript==
// @name         Facebook Otomatik Takipten Cikma
// @namespace    http://tampermonkey.net/
// @version      0.2
// @description  Facebook Otomatik Takipten Cikma
// @author       Deniz KOD
// @match        *://*.facebook.com/*
// @grant        none
// ==/UserScript==


(function() {
    'use strict';

    let intervalID = null;

    function unfollowDirectly() {
        let followButtons = document.querySelectorAll('span.x1lliihq.x6ikm8r.x10wlt62.x1n2onr6.xlyipyv.xuxw1ft');

        followButtons.forEach(button => {
            if (button.textContent === "Takiptesin") {
                console.log('Attempting to click unfollow on:', button);
                button.click();
                setTimeout(clickUnfollow, 500); // Short delay to allow for the confirmation dialog to appear
            }
        });
    }

    function clickUnfollow() {
        let unfollowButtons = document.querySelectorAll('span.x193iq5w.xeuugli.x13faqbe.x1vvkbs.x1xmvt09.x1lliihq.x1s928wv.xhkezso.x1gmr53x.x1cpjm7i.x1fgarty.x1943h6x.xudqn12.x3x7a5m.x6prxxf.xvq8zen.xk50ysn.xzsf02u.x1yc453h');
        unfollowButtons.forEach(button => {
            if (button.textContent.includes("Takibi Bırak")) {
                console.log('Confirmed unfollow on:', button);
                button.click();
            }
        });
    }

    document.addEventListener('keydown', function(e) {
        if (e.keyCode === 113 && !intervalID) { // F2 to start
            console.log('Unfollow script activated.');
            intervalID = setInterval(unfollowDirectly, 2000); // Adjust this interval as necessary
        } else if (e.keyCode === 115 && intervalID) { // F4 to stop
            console.log('Unfollow script deactivated.');
            clearInterval(intervalID);
            intervalID = null;
        }
    });
})();
```

## NASIL ÇALIŞIR?

![image](https://github.com/DenizKod/Facebook-Otomatik-Takipten-Cikma/assets/168285638/e73c82ce-c667-4d02-9cf8-bc4c96f841e6)

### iŞLEME BAŞLAMADAN ÖNCE OKU !

<p>- Eğer takip ettiğiniz kişiler listesinde kişilerin üstünde "İsteği İptal Et" yazıyorsa onlar 10 saniye'de toplu iptal etme koduda mevcut</p>

### TOPLU İSTEĞİ İPTAL ETME KODU : https://github.com/DenizKod/Gonderilen-ark-isteklerini-toplu-iptal-etme

![image](https://github.com/DenizKod/Facebook-Otomatik-Takipten-Cikma/assets/168285638/37b29ae5-e6cd-4513-b6d8-ab3491f45b25)

### TAKİPTEN ÇIKMA İŞLEMİNE DEVAM EDELİM !

<p>- Öncelikle işlem yarı otomatik olarak çalışıyor</p>
<p>- F2 tuşu başlatır F4 tuşu işlemi durdurur</p>
<p>- İşlemi başlatığınızda kişilerin üstüne mouse tuttuğunuzda Profil kartı açılır ve Takiptesin butonu gözükür. Bot o anda hızlı bir şekilde "Takiptesin" butonuna tıklar ve "Takipten çıkar" yapar</p>

![image](https://github.com/DenizKod/Facebook-Otomatik-Takipten-Cikma/assets/168285638/0204aa15-4a02-4b63-a81f-e8e128b7f6d5)
