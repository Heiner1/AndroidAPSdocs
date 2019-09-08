# Budoucí (možné) ovladače pump

Toto je seznam vybraných pump, které jsou v oběhu mezi diabetiky, a stav jejich podpory vůči jakémukoliv systému uzavřené smyčky a stav podpory vůči AAPS. Na konci stránky jsou informace, co je po pumpě vyžadováno, aby byla použitelná pro uzavřenou smyčku.

## Pumpy, na jejichž podpoře se pracuje

### Medtronic

**Stav smyčky:** Některé starší verze pump jsou pro uzavřenou smyčku použitelné, ale nikoliv jejich novější modely (viz níže).

**Jiné implementace:** OpenAPS, Loop

**Java implementace:** Částečná implementace dostupná [Roundrtrip2](https://github.com/TC2013/Roundtrip2) a [RileyLinkAAPS](https://github.com/andyrozman/RileyLinkAAPS)

**Stav implementace AAPS:** Probíhající práce. Více viz [Andyho fork AndroidAPS](https://github.com/andyrozman/AndroidAPS), branch medtronic_andy. Většina práce byla provedena v souvislosti s [RileyLinkAAPS](https://github.com/andyrozman/RileyLinkAAPS), aby fungoval framework a příkazy. V daném úložišti je projekt (Medtronic) a otevřené tikety pro budoucí vývoj, vývoj probíhá na branchi dev_medtronic (což je zde výchozí branch). K dispozici je také místnost na gitteru: RileyLinkAAPS/Lobby. AAPS. 0.10 testovací verze "release" je vydána, obsahuje přibližně 95 % všech funkcí, v současnosti však chybí synchronizace dočasných bazálů a událostí pumpy "Výdej zastaven". Project pravděpodobně bude koncem července 2019 sloučen do hlavního úložiště. Podrobnosti a termíny viz [Přehled projektu](https://github.com/andyrozman/RileyLinkAAPS/projects/1).

**Hardwarové požadavky pro AAPS:** RileyLink (s 916MHz anténou).

** Verze s podporou uzavřené smyčky:** 512-522, 523 (firmware 2.4A nebo nižší), 554 (EU firmware 2.6A nebo nižší, CA firmware 2.7A nebo nižší). Totéž platí pro 7xx verze. Všechna ostatní zařízení nejsou podporovaná a pravděpodobně ani nebudou.

* * *

### Insulet Omnipod (se starými Eros Pods) ([Domovská stránka](https://www.myomnipod.com/en-gb/about/how-to-use))

**Stav smyčky:** V současnosti chybí nativní podpora AAPS. Dekódování protokolu Omnipod je dokončeno- [OpenOmni](http://www.openomni.org/) a [OmniAPS Slack](https://omniaps.slack.com/)

**Ostatní implementace:**

- Omnipy for AndroidAPS (stabilní verze se testuje, vyžaduje Raspberry Pi i RileyLink a speciálně upravneou verzi AndroidAPS) [Omnipy](https://github.com/winemug/omnipy)
- OmniCore for AndroidAPS (dosud nevydáno, C# kód běžící "nativně" na Androidu, vyžaduje pouze RileyLink a speciálně upravenou verzi AndroidAPS - příští verze projektu Omnipy). [OmniCore](https://github.com/winemug/OmniCore)
- Loop (stabilní, vydáno, vyžaduje RileyLink). [Loop](https://loopkit.github.io/loopdocs/)

**Java implementace:** Prozatím žádné.

**Stav implementace AAPS:** Začaly práce na [RileyLinkAAPS](https://github.com/bartsopers/RileyLinkAAPS/) for Omnipod (dev_omnipod branch), který nebude vyžadovat Raspberry Pi, prozatím nedokončeno. Postup můžete sledovat na https://omniaps.slack.com/ kanál android-driver.

**Hardwarové požadavky pro AAPS:** RileyLink s Omnipod firmware (2.x) a 433MHz anténou.

## Pumpy, které lze provozovat se smyčkou

### Omnipod DASH ([Domovská stránka](https://www.myomnipod.com/DASH))

**Stav smyčky:** Aktuálně nepodporovaná žádným systémem smyčky. Pumpa je kandidátem pro smyčku, ale protokol je v současnosti neznámý. Prodej pumpy byl oficiálně zahájen v lednu 2019.

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Podporuje bluetooth.

**Komentáře:** Uvažujeme o vývoji pro Omnipod DASH, problémem však je, že pumpa Dash v současnosti není dostupná v Evropě (kde se nachází většina vývojářů AAPS) a že komunikační protokol je neznámý. Pokusíme se pomocí reverzního inženýrství oficiálního souboru Dash APK zjistit, jak komunikace funguje a poté na základě těchto zjištění realizujeme implementaci. Postup můžete sledovat zde: [DashAAPS](https://github.com/andyrozman/DashAAPS/projects/1), ale neočekávejte dostupnost v brzké době. V současné době jsme pouze ve fázi ověřování proveditelnosti (dokud nebude splněn Milestone 2).

* * *

### Pumpa Ypsomed ([Domovská stránka](https://www.ypsomed.com/en/diabetes-care-mylife.html))

**Stav smyčky:** Verze 1 - 1.5 (2. kvartál/2018) nejsou kandidáti pro smyčku. Přestože mají bluetooth komunikaci, zdá se, že je rozsah komunikace velmi limitovaný (jednosměrný: pumpa -> aplikace). Možná se to v budoucích verzích změní.

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Podporuje bluetooth.

* * *

### Kaleido ([Domovská stránka](https://www.hellokaleido.com/))

**Stav smyčky:** Aktuálně nepodporovaná žádným systémem smyčky. Pumpa je kandidátem na smyčku, ale jelikož je zatím neznámý její komunikační protokol, nezdá se, že by tato pumpa byla brzy podporovaná.

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Podporuje bluetooth.

* * *

### Medtrum A6/P6/C6 ([Domovská stránka](http://www.medtrum.com/P6.html))

**Stav smyčky:** Je kandidátem na smyčku. Společnost má svůj vlastní omezený systém polosmyčky (A6). Ovládání přes aplikaci pro iPhone. Žádná aplikace pro Android v současné době není dostupná.

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Zdá se, že podporuje BT.

* * *

### EOFLOW ([Domovská stránka](http://www.eoflow.com/eng/main/main.html))

**Stav smyčky:** Je kandidátem na smyčku. Dálkové ovládání, které používá, je ve skutečnosti upraveným zařízením se systémem Android. (Pumpa je v současnosti dostupná pouze v Koreji).

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Zdá se, že podporuje BT.

* * *

### Accu-Chek Solo ([Domovská stránka](https://www.roche.com/media/releases/med-cor-2018-07-23.htm))

**Stav smyčky:** Je kandidátem na smyčku. Pumpa se koncem roku 2018 začne prodávat ve vybraných zemích EU. Proslýchá se, že ji bude možné ovládat pomocí aplikace pro Android.

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Zdá se, že podporuje BT.

### Medtronic Bluetooth

**Komentáře:** Tato pumpa má přijít během několika příštích let a plánuje se, že bude podporovat software Tidepool Loop ([viz tento článek](https://www.tidepool.org/blog/tidepool-loop-medtronic-collaboration).

* * *

## Pumpy, které již nejsou v prodeji (společnosti již nefungují)

### Pumpa Cellnovo ([Domovská stránka](https://www.cellnovo.com/en/homepage))

**Stav smyčky:** Aktuálně nepodporovaná žádným systémem smyčky. Pumpa je kandidátem na smyčku, ale jelikož je zatím neznámý její komunikační protokol, nezdá se, že by tato pumpa byla brzy podporovaná.

**Hardwarové požadavky pro AAPS:** Zřejmě žádné. Podporuje bluetooth.

**Poznámka k produktu:** Zdá se, že společnost se rozhodla opustit trh s pumpami. Více informací viz tento [článek](https://diabetogenic.wordpress.com/2019/04/01/and-then-cellnovo-disappeared/?fbclid=IwAR12Ow6gVbEOuD1zw7aNjBwqj5_aPkPipteHY1VHBvT3mchlH2y7Us6ZeAU)

## Pumpy, které nelze provozovat se smyčkou

### Tandem:(všechny) ([Domovská stránka](https://www.tandemdiabetes.com/))

**Stav smyčky:** Nelze použít pro smyčku.

Před časem měli firmware zvaný T:AP (zmiňovaný v tomto [článku](https://www.liebertpub.com/doi/full/10.1089/dia.2018.0278?url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org&rfr_dat=cr_pub%3Dpubmed&), který by bylo možné použít se smyčkou (již není k dispozici, pumpy byly upgradovány na firmware x2), ten však nebyl určen pro komerční použití, ale pouze pro experimentální účely (výzkumné projekty). Hovořil jsem s jedním z ředitelů společnosti a ujistil mě, že pumpa Tandem nikdy nebude otevřená, ale že vytvořili svou vlastní uzavřenou smyčku, které říkají Control-IQ (domnívám se, že je již dostupná v USA a v EU by měla být dostupná v roce 2020).

* * *

### Animas Vibe

**Stav smyčky:** Nelze použít pro smyčku. Není k dispozici dálkový ovladač. **Poznámka:** Pumpa se již neprodává. Společnost opustila trh s pumpami (J&J).

* * *

### Animas Ping

**Stav smyčky:** Nelze použít pro smyčku. Dokáže vydávat bolusy, ale ne dočasné bazály. **Poznámka** Přestala se prodávat s příchodem modelu Vibe.

## Požadavky na pumpu, aby podporovala smyčku

**Předpoklady**

- Pumpa musí podporovat dálkové ovládání (nějakou formou) (BT, rádiovou frekvencí atd.)
- Komunikační protokol je hacknutý/zdokumentovaný/atd.

**Minimální požadavky**

- Nastavení dočasné bazální dávky
- Zjištění stavu
- Zrušení dočasné bazální dávky

**Pro oref1 (SMB) nebo posílání bolusů:**

- Poslat bolus

**Hodilo by se**

- Zrušit bolus
- Načíst bazální profil (prakticky nutnost)
- Nastavit bazální profil (příjemný bonus)
- Číst historii 

**Ostatní (není vyžadováno, ale hodí se)**

- Nastavit prodloužený bolus
- Zrušit prodloužený bolus
- Číst historii
- Číst TDD

* * *

### Podpora ostatních pump

Jestliže máte jinou pumpu a chtěli byste k ní znát stav podpory, prosím kontaktujte mě (andyrozman na gitteru). Řada pump (a jejich konfigurací) bude v budoucí verzi přidána jako "použitelné s otevřenou smyčkou" (budete moci vybrat typ virtuální pumpy v konfiguraci a vaše nastavení bude načteno - [Požadavek #863](https://github.com/MilosKozak/AndroidAPS/issues/863)).