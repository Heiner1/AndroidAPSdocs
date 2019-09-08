Übersicht der Komponenten 
==============================================
AndroidAPS ist nicht einfach eine (selbst erstellte) App, es ist eines von verschiedenen Modulen Deines Closed Loop Systems. Bevor Du Dich für die einzelnen Komponenten entscheidest, solltest Du einen Blick auf das `Komponenten-Setup <https://androidaps.readthedocs.io/en/dev/EN/index.html#component-setup>`_ werfen..
   
.. image:: ../images/modules.png
  :alt: Übersicht der Komponenten

.. note:: 
   **WICHTIGER SICHERHEITSHINWEIS**

   Die grundlegenden Sicherheitsfunktionen von AndroidAPS, die in dieser Dokumentation beschrieben sind, bauen auf den Sicherheitsfunktionen der Hardware auf, mit der du dein System aufgesetzt hast. Es ist extrem wichtig, dass die Insulinpumpe und das CGM-System, die für ein Closed Loop System mit automatisierter Insulinabgabe verwendet werden, hinreichend getestet und voll funktionstüchtig sind sowie (in Europa) eine CE-Kennzeichnung haben und (in Deutschland) als Medizinprodukte zugelassen sind. Veränderungen an Hard- oder Software dieser Komponenten können zu unerwarteter Insulinabgabe und damit zu erheblichen Risiken für den Anwender führen. *Verwende keine* defekten, modifizierten oder selbsterstellten Insulinpumpen oder CGM-Empfänger, um ein AndroidAPS-System zu erstellen oder zu betreiben.

   Außerdem ist es ebenso wichtig, nur Originalzubehör zu verwenden. Setzhilfen, Kanülen und Reservoire müssen vom Hersteller für den Einsatz mit deiner Pumpe bzw. deinem CGM zugelassen sein. Die Verwendung von nicht geprüftem oder modifiziertem Zubehör kann zu Ungenauigkeiten des CGM-Systems und Insulinabgabefehlern führen. Insulin ist sehr gefährlich, wenn es falsch dosiert wird. Spiele nicht mit deinem Leben, indem du ungeprüftes oder modifiziertes Zubehör verwendest.

Notwendige Fähigkeiten
=====================
Gute individuelle Profileinstellungen für Deine Diabetes-Therapie
------------------
Obwohl Du es weder kaufen noch einfach erstellen kannst, ist dies wahrscheinlich das Modul, das am meisten unterschätzt wird, obwohl es für einen funktionieren Loop absolut wesentlich ist. Wenn Dich der Algorithmus bei Deinem Diabetes-Management unterstützen soll, benötigt dieser die korrekten Einstellungen um keine schwerwiegenden Fehlentscheidungen zu treffen.
Auch wenn Dir andere Module noch fehlen, kannst Du Dein bestehendes 'Profil' zusammen mit Deinem Diabetes-Team überprüfen und anpassen. 
Die meisten Looper verwenden eine sogenannte zirkadiane Basalrate, Korrektur- und KH-Faktoren die sich an der hormonellen Insulinempfindlichkeit im Tagesverlauf orientieren.

Das Profil beinhaltet:

* BR (Basalraten)
* ISF (insulin sensitivity factor - Korrekturfaktor): Menge an mg bzw. mmol die eine Einheit Insulin Deinen Blutzucker senkt
* CR (carb ratio - KH-Faktor): Gramm Kohlenhydrate, die mit einer Einheit Insulin abgedeckt werden können
* DIA (duration of insulin acting): Insulin-Wirkdauer

Smartphone
-------
Du benötigst ein Android Smartphone mit Android 6.0 oder höher. Es gibt eine von AAPS Anwendern erstellte `Liste mit getesteten Smartphones und Smartwatches: <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_

Um ein Handy oder eine Smartwatch einzutragen welches noch nicht in der Liste ist, bitte das  `Formular <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_ ausfüllen.

Probleme mit der Tabelle bitte per E-Mail an `hardware@androidaps.org <mailto:hardware@androidaps.org>`_melden. Wenn du Handys oder Smartwatches zum Testen zur Verfügung stellen möchtest, bitte eine E-Mail an `donations@androidaps.org <mailto:hardware@androidaps.org>`_ schreiben.

Insulinpumpe
--------
AndroidAPS funktioniert **derzeit** mit 

- `Accu-Chek Combo <../Configuration/Accu-Chek-Combo-Pump.html>`_ (additionally needed: Ruffy app, LineageOS or Android 8.1 on your phone)
- `Accu-Chek Insight <../Configuration/Accu-Chek-Insight-Pump.html>`_ 
- `DanaR <../Configuration/DanaR-Insulin-Pump.html>`_ 
- `DanaRS <../Configuration/DanaRS-Insulin-Pump.html>`_  
- `einigen alten Medtronic Pumpen <../Configuration/MedtronicPump.html>`_ ab der neuen Version 2.4 (zusätzlich werden RileyLink/Gnarl Hardware und ein Android Smartphone mit Bluetooth Low Energy (BLE-Chipset) benötigt.)

**Andere Pumpen,** die zukünftig möglicherweise von AndroidAPS unterstützt werden können, sind auf der Seite `Zukünftig ggf. loopbare Pumpen <Future-possible-Pump-Drivers.html>`_ aufgeführt.

Falls Du eine Pumpe **auf eigene Kosten** erwerben willst, findest Du in `dieser Tabelle <https://drive.google.com/open?id=1CRfmmjA-0h_9nkRViP3J9FyflT9eu-a8HeMrhrKzKz0>`_ die Adressen der Anbieter in verschiedenen Ländern. Ergänze bitte die Angaben zu Deinem Händler, falls dieser dort noch nicht aufgeführt ist.

**Welche Pumpe ist am Besten für den Closed Loop mit AndroidAPS geeignet?**

Die Combo, die Insight und die älteren Medtronic Pumpen sind solide und "loopfähig". Die Combo hat wegen des Standard Luer-Lock-Anschlusses auch den Vorteil, dass die Auswahl an Kathetern groß ist. Und sie verwendet Standard-Batterien, die rund um die Uhr an jeder Tankstelle erhältlich sind. Im Notfall kannst du sie sogar aus der Fernbedienung in deinem Hotelzimmer "ausleihen" ;-)

Die Vorteile der Dana R/RS gegenüber  der Combo sind aber:

- Die DanaR/RS kann sich mit fast jedem Smartphone verbinden, auf dem das Betriebssystem Google Android >= 5.1 installiert ist. Ein Austausch der werksseitigen Smartphone-Software (z. B. durch das Lineage Betriebssystem) ist nicht nötig. Wenn dein Smartphone kaputt geht oder gestohlen wird, kannst du auf einem anderen / neuen Smartphone sehr schnell die Pumpe wieder steuern... Mit der Combo ist das nicht so einfach,  jedenfalls nicht solange Android 8.1 nur auf wenigen Smartphones installiert ist.
- Das erste Einrichten der Verbindung zwischen der DanaR/RS und dem Smartphone ist einfacher. Allerdings ist dieser Schritt normalerweise nur bei der Ersteinrichtung erforderlich.
- Bislang arbeitet die Combo mit screen parsing. Grundsätzlich funktioniert das gut, aber es ist leider langsam. Beim Loopen ist das nicht so schlimm, denn das läuft alles im Hintergrund ab. Das führt aber dazu, dass eine bestehende Bluetooth-Verbindung leichter abgebrochen wird. Das kann unpraktisch sein, wenn du dich während eines Bolus-Prozesses zu weit vom Smartphone entfernst (z. B. beim Kochen). 
- Die Combo virbiert am Ende jeder TBR, die DanaR vibriert (oder piept) bei Abgabe eines SMB. In der Nacht wird der Loop meistens eher TBR setzen statt SMB.  Die DanaRS kann so eingestellt werden, dass sie weder bei TBR, noch bei SMB vibriert oder piept.
- Die History kann auf der DanaRS in wenigen Sekunden mit COB ausgelesen werden. Deshalb können die Smartphones offline leicht ausgewechselt werden. Sobald einige CGM-Daten verfügbar sind, kann das Loopen fortgesetzt werden.
- Alle Pumpen, die AndroidAPS unterstützt, sind (jedenfalls bei Auslieferung) wasserdicht. Nur die DanaR/Rs garantiert auch während der Nutzung Wasserdichtigkeit durch das abgedichtete Batteriefach und das Reservoir-System. 

BZ-Quelle
------------
Dies ist nur eine knappe Übersicht über alle kompatiblen CGM/FGM mit AndroidAPS. Weitere Details findest Du `hier <../Configuration/BG-Source.html>`_. Nur ein kurzer Hinweis: Wenn Du Deine Glukose-Daten in der xDrip+ App oder Deiner Nightscout-Website anzeigen kannst, kannst Du xDrip+ (oder Nightscout mit Webverbindung) als BZ-Quelle in AAPS wählen.

* Dexcom G4: Diese Sensoren sind relativ alt, aber es gibt im Netz Anleitungen wie Du sie mit der xDrip+ App verwenden kannst.
* Dexcom G5 funktioniert mit der xDrip+ App oder der gepatchten Dexcom App.
* Dexcom G6 funktioniert mit der xDrip+ App oder der gepatchten Dexcom App.
* Libre 1: Du benötigst einen Sender wie Bluecon oder MiaoMiao, den Du selbst bauen oder einfach kaufen kannst, und die xDrip+ App.
* Libre 2 funktioniert direkt ohne weitere Hardware mit xDrip+ (no transmitter needed), aber Du musst Dir selbst die gepatche Libre 2 app erstellen. In dieser `Anleitung <https://github.com/user987654321resu/Libre2-patched-App>`_ findest Du weitere Details.
* Eversense funktioniert bisher nur in Kombination mit der ESEL-App und einer gepatchten Eversense-App (funktioniert nicht mit der Kombination Dana RS und LineageOS, jedoch gut mit DanaRS und Android oder Combo und Lineage OS).
* Enlite: ziemlich kompliziert mit vielen zusätzlichen Sachen


Nightscout
------------
Nightscout ist eine Open Source Web-Anwendung, die Deine CGM-Daten und AndroidAPS-Daten protokollieren und anzeigen kann und Berichte erstellt. Mehr Informationen findest Du auf der `Website des Nightscout-Projekts <http://www.nightscout.info/>`_. Du kannst deine eigene Nightscout-Website mit Hilfe von `Heroko <http://www.nightscout.info/wiki/welcome/set-up-nightscout-using-heroku>`_ erstellen, die halbautomatische Nightscout-Einrichtung auf `zehn.be <https://ns.10be.de/en/index.html>`_ oder auf deinem eigenen Server hosten (dies ist für IT-Experten).

Nightscout ist unabhängig von den anderen Modulen. Du brauchst aber auf jeden Fall eine Nightscout-Seite, um das Objetive (Ziel) 1 abzuschließen.

Weitere Informationen zur Konfiguration von Nightscout für die Verwendung mit AndroidAPS findest Du `hier <../Installing-AndroidAPS/Nightscout.html>`_.

AAPS-.apk Datei
---------------
Die grundlegende Komponente des Systems. Bevor Du die App installierst, musst Du zuerst die apk-Datei (das ist Dateinamenerweiterung für eine Android-App) erstellen. Die Anleitung dazu findest Du  `hier <../Installing-AndroidAPS/Building-APK.html>`_.  

Optionale Module
==================
Smartwatch
---------------
Jede Smartwatch mit Android 1.x oder höher funktioniert. Viele Looper verwenden eine Sony Smartwatch 3 (SWR50), da diese auch Werte vom Dexcom G5/G6 empfangen kann, wenn sich das Smartphone nicht in Reichweite befindet. Einige andere Smartwatches können so gepatched werden, dass sie als 'Standalone receiver' verwendet werden können (siehe `diese Dokumentation <https://github.com/NightscoutFoundation/xDrip/wiki/Patching-Android-Wear-devices-for-use-with-the-G5>`_ für weitere Details).

Es gibt eine von AAPS Anwendern erstellte `Liste mit getesteten Smartphones und Smartwatches: <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_. Es gibt verschiedene Watchfaces zur Nutzung mit AndroidAPS, weitere Informationen findest Du `hier <../Configuration/Watchfaces.html>`_.

Um ein Handy oder eine Smartwatch einzutragen welches noch nicht in der Liste ist, bitte das  `Formular <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_ ausfüllen.

Probleme mit der Tabelle bitte per E-Mail an `hardware@androidaps.org <mailto:hardware@androidaps.org>`_melden. Wenn du Handys oder Smartwatches zum Testen zur Verfügung stellen möchtest, bitte eine E-Mail an `donations@androidaps.org <mailto:hardware@androidaps.org>`_ schreiben.

xDrip+
-------
Auch wenn Du die xDrip+ App nicht als BZ-Datenquelle benötigst, kannst Du sie dennoch für  Alarme oder eine gute Anzeige der Glukosewerte verwenden. Du kannst in xDrip+ beliebig viele Alarme einreichten, festlegen zu welchen Zeiten diese aktiv sein sollen, ob sie die Stummschaltung des Smartphones überschreiben können etc. Weitere Hinweise zu den xDrip+ Einstellungen findest Du `hier <../Configuration/xdrip.html>`_. Beachte bitte, dass die Entwicklung von xDrip+ sehr agil ist und die Dokumentation damit teilweise nicht Schritt halten und entsprechend nicht immer aktuell sein kann.

Konfigurationsbeispiel
============
Eine Schritt-für-Schritt-Anleitung findest Du im Sample Setup. Dieses ist schon etwas älter, die Vorgehensweise ist aber noch aktuell.

.. toctree::
   :maxdepth: 1
   :glob:
   
   Sample Setup <../Getting-Started/Sample-Setup.html>
 
  
Wartezeit überbrücken
============================================
Manchmal dauert es eine Weile, um alle Module für den Closed Loop zusammen zu bekommen. Aber keine Sorge, es gibt viele Dinge, die Du in der Zwischenzeit machen kannst. Es ist ABSOLUT WICHTIG, Deine Basalrate (BR), die KH-Faktoren (IC), Korrekturfaktoren (ISF) etc. intensiv zu prüfen und ggf. anzupassen. Der Open Loop ist zudem eine sehr gute Möglichkeit, das System kennenzulernen und mit AndroidAPS vertraut zu werden. Im Open Loop gibt AndroidAPS Behandlungsempfehlungen, die Du manuell umsetzen musst.

Du kannst Dich weiter durch das Wiki arbeiten, online und offline mit anderen Loopern in Kontakt treten, weitere `Hintergrundinfos <https://androidaps.readthedocs.io/en/dev/EN/Where-To-Go-For-Help/Background-reading.html>`_ oder Berichte von anderen Loopern lesen. Sei aber vorsichtig, nicht alle Anwenderberichte müssen richtig oder für Deinen Fall zutreffend sein.

**Fertig?**
Wenn Du alle Komponenten für AAPS zusammen hast - oder zumindest genug, um mit dem Open Loop zu beginnen - solltest Du zuerst die Beschreibung der `Objectives (Ziele) <../Usage/Objectives.html>`_ lesen und Deine `Hardware <../index.html#component-setup>`_ einrichten. Lies Dir nach dem Erreichen eines Objectives (Ziel) auf jeden Fall nochmals durch, was im nächsten Schritt passiert.
