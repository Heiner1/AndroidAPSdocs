# Profiel wissel

Bij het in gebruik nemen van AndroidAPS, moet je een profiel selecteren en ook een "Profiel wissel" doen met een duur van nul minuten (wordt verderop uitgelegd). Hierdoor begint AAPS met het bijhouden van jouw profiel geschiedenis. Elke keer wanneer je iets aan je profiel verandert dan zul je opnieuw een "Profiel wissel" moeten doen om deze wijzigingen te activeren. Wanneer je Nightscout profielen gebruikt en je jouw profiel hebt gewijzigd dan worden deze wijzigingen direct naar AAPS doorgestuurd, maar vergeet niet om een "Profiel wissel" te doen in NS of AAPS om de wijzigingen te activeren (zelfs al heb je wijzigingen doorgevoerd aan je actieve profiel).

Wanneer je een Profiel wissel doet, dan maakt AAPS een momentopname van jouw profiel, met een startdatum en een tijdsduur en gebruikt dit profiel binnen deze door jou gespecificeerde periode. Een tijdsduur van nul betekent 'oneindig lang'. Dan wordt dat profiel gebruikt totdat je een volgende Profiel wissel doet. Je hoeft overigens geen nul in te vullen, het vakje leeg laten kan ook.

Als je wel een tijdsduur invult bij de Profiel wissel, dan zal AAPS na afloop weer terugschakelen naar het profiel dat actief was vóórdat je de tijdelijke Profiel wissel deed.

Wanneer je lokale AAPS profielen gebruikt (Eenvoudig, Lokaal) dan moet je ook steeds een Profiel wissel uitvoeren nadat je iets aan jouw profiel hebt gewijzigd. Anders zullen je wijzigingen niet actief worden.

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