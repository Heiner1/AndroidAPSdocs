# Přepínání profilu

Po prvním spuštění AndroidAPS a výběru profilu budete potřebovat ještě provést "Přepnutí profilu" s nulovým trváním (viz dále). Tím začne AAPS sledovat historii profilů a každá nová změna profilu vyžaduje další "Přepnutí profilu", přestože změny na profilu provádíte v Nightscoutu. Aktualizovaný profil je do AAPS načtený okamžitě, ale potřebujete ještě přepnutí stejného profilu (v NS nebo AAPS), abyste tyto změny začali reálně používat.

AAPS si vnitřně dělá snímek profilu s datumem zahájení a s trváním a používá ho v rámci stanovené doby. Nulové trvání znamená nekonečně (pořád). Takový profil je platný až do dalšího "Přepnutí profilu".

Pokud použijete "Přepnutí profilu" s určením doby, profil se automaticky po uplynutí času přepne zpět do posledního platného "Přepnutí profilu"

Pokud používáte lokální AAPS profily (jednoduchý, místní, CPP), musíte stisknout tlačítko, abyste změny použili (vytvoří to správnou událost "Přepnutí profilu").

Within the "profile switch" you can choose two additional changes which used to be part of the Circadian Percentage Profile:

## Percentage

* This applies the same percentage to all parameters. 
* If you set it to 130% (meaning you are 30% more insulin resistant), it will raise the basal rate by 30%. It will also lower the ISF and IC accordingly (divide by 1.3 in this example). 
* It will be sent to the pump and then be the default basal rate. 
* The loop algorithm (open or closed) will continue to work on top of the selected percentage profile. So for example separate percentage profiles can be set up for different stages of the hormone cycle.

## Timeshift

* This moves everything round the clock by the number of hours entered. 
* So for example, when working night shifts change the number of hours to how much later/earlier you go to bed or wake up.
* It is always a question of which hour's profile settings should replace the settings of the current time. This time must be shifted by x hours. So be aware of the directions as described in the following example: 
  * Current time: 12:00
  * **Positive** timeshift 
    * 2:00 **+10 h** -> 12:00
    * Settings from 2:00 will be used instead of the settings normally used at 12:00 because of the positive timeshift.
  * **Negative** timeshift 
    * 22:00 **-10 h** -> 12:00
    * Settings from 22:00 (10 pm) will be used instead of the settings normally used at 12:00 because of the negative timeshift.

![Profile switch timeshift directions](../images/ProfileSwitch_PlusMinus.png)

This mechanism of taking snapshots of the profile allows a much more precise calculations of the past and the possibility to track profile changes.

## Troubleshooting Profile Errors

* 'Invalid profile' or 'Basal Profile not aligned to hours' error message will appear if you have any basal rates or I:C rates not on the hour. The DanaR and DanaRS pumps do not support changes on the half hour.
* 'Received profile switch from NS but profile does not exist locally' or Go either to Treatments tab in AndoridAPS and select Profile Switch, 'remove' the date and time that was mentioned in the error message. Or go to your mlab collection, search in the treatments for profile switch and delete the date and time that was mentioned in the error message. ![mlab](https://files.gitter.im/MilosKozak/AndroidAPS/I5am/image.png)
* 'DIA 3hr too short' error message will appear if your duration of insulin action in your profile is listed at a value that AndroidAPS doesn't believe will be accurate. Read about [selecting the right DIA](http://www.diabettech.com/insulin/why-we-are-regularly-wrong-in-the-duration-of-insulin-action-dia-times-we-use-and-why-it-matters/), and edit it in your profile then do a Profile Switch to continue.