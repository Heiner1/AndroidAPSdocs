Willkommen zur AndroidAPS-Dokumentation
==============================================

AndroidAPS ist eine Open Source App für Google Android Smartphones, die bei insulinabhängigem Diabetes als künstliche Bauchspeicheldrüse (sog. artificial pancreas system - APS) dient. Hauptkomponenten sind verschiedene OpenAPS-Softwarealgorithmen, die genau das zu tun sollen, was eine echte Bauchspeicheldrüse auch tut: den Blutzuckerspiegel durch automatisierte Insulindosierung (AID) in gesunden Grenzen halten. Zusätzlich werden zumindest eine unterstützte Insulin-Pumpe und ein CGM benötigt, die eine CE-Kennzeichnung haben. Die App hat KEINE selbstlernende künstliche Intelligenz. Stattdessen basieren die Berechnungen von AndroidAPS auf den individuellen Therapiefaktoren und Kohlenhydratmengen, die der Benutzer manuell in sein Behandlungsprofil eingibt. Diese Eingaben werden aber aus Sicherheitsgründen vom System verifiziert. Die App wird nicht in Google Play angeboten - du musst sie aus rechtlichen Gründen selbst aus dem Quellcode erstellen.

Hauptkomponenten sind:

.. image:: images/modules-female.png
  :alt: Komponenten

Für weitere Details lies bitte hier weiter.

Erste Schritte
----------------
.. toctree::
   :maxdepth: 1
   :glob:
   
   Sicherheitshinweise <./Getting-Started/Safety-first.rst>
   Was ist ein Closed Loop System <./Getting-Started/ClosedLoop.rst>
   Was ist ein Closed Loop System mit AndroidAPS <./Getting-Started/WhatisAndroidAPS.rst>  
   
   
Was brauche ich 
-----------------------------------------
.. toctree::
   :maxdepth: 1
   :glob:
   
   Module <./Module/module.rst>

   
AndroidAPS installieren
------------
.. toctree::
   :maxdepth: 1
   :glob:

   App aus Quellcode erstellen <./Installing-AndroidAPS/Building-APK.md>
   Update auf neue Version oder Branch <./Installing-AndroidAPS/Update-to-new-version.md>
   Release Notes <./Installing-AndroidAPS/Releasenotes.md>
   Dev branch (nur für Entwickler) <./Installing-AndroidAPS/Dev_branch.md>
   
   
Komponenten-Setup
---------------
.. toctree::
   :maxdepth: 1
   :glob:
   
   CGM/FGM <./Configuration/BG-Source.rst>
   xDrip Einstellungen <./Configuration/xdrip.md>
   Pumpen <./Hardware/pumps.rst>
   Smartphones <./Hardware/Phoneconfig.rst>
   Nightscout Installation <./Installing-AndroidAPS/Nightscout.md>
   Smartwatch  <./Hardware/Smartwatch.rst>
   

AndroidAPS einrichten 
---------------
.. toctree::
   :maxdepth: 1
    
   
   Konfigurations-Generator <./Configuration/Config-Builder.md>
   Einstellungen im Drei-Punkte-Menü <./Configuration/Preferences.md>
   
   
AndroidAPS Nutzung
------------
.. toctree::
   :maxdepth: 1
       
    
   AndroidAPS-Bildschirme <./Getting-Started/Screenshots.md>
   Objectives (Ziele) <./Usage/Objectives.md>
   OpenAPS-Funktionen <./Usage/Open-APS-features.md>   
   Empfindlichkeitserkennung und COB <./Configuration/Sensitivity-detection-and-COB.md>
   Profil Wechsel <./Usage/Profiles.md>
   Temporäre Ziele <./Usage/temptarget.md>   
   Verzögerte Kohlenhydrate (eCarbs) <./Usage/Extended-Carbs.md>
   Automation <./Usage/Automation.rst>
  
 
Allgemeine Hinweise 
---------------------
.. toctree::
   :maxdepth: 1
   :glob:
   
   Zeitzonenwechsel auf Reisen <./Usage/Timezone-traveling.md>
   Logfiles erhalten <./Usage/Accessing-logfiles.md>
   Accu Chek Combo - Tipps <./Usage/Accu-Chek-Combo-Tips-for-Basic-usage.md> 
   Export/Import von Einstellungen <./Usage/ExportImportSettings.rst>
   

AndroidAPS für Kinder
------------------
.. toctree::
   :maxdepth: 1
   :glob:
   
   SMS-Befehle <./Usage/SMS-Commands.md>
   

Für Fortgeschrittene 
----------
.. toctree::
   :maxdepth: 1
   :glob:
   
   Android Auto <./Usage/Android-auto.md>
   Automation mit Drittanbieter-Apps <./Usage/automationwithapp.md>
   

Problembehandlung
------------------------------------------
.. toctree::
   :maxdepth: 1
   :glob:
  
   Nightscout Client <./Usage/Troubleshooting-NSClient.md>
   Update <./Installing-AndroidAPS/Update-to-new-version.html#troubleshooting>
   Pumpen <./FGT/Troubleshootingpumps.rst>


FAQ 
------------------------------------------
.. toctree::
   :maxdepth: 1
   :glob:
  
   FAQ <./Getting-Started/FAQ.md>

   
Glossar
------------------------------------------
.. toctree::
   :maxdepth: 1
   :glob:
  
   Glossar <./Getting-Started/Glossary.md>
  

Hilfe durch die Community 
------------
.. toctree::
   :maxdepth: 1
   :glob:

   Nützliche Informationsquellen vor dem Start <./Where-To-Go-For-Help/Background-reading.md>
   Hilfe <./Where-To-Go-For-Help/Connect-with-other-users.md>

Für Mediziner & Fachpersonal
------------
.. toctree::
   :maxdepth: 1
   :glob:
            
   Für Mediziner & Fachpersonal <./Resources/clinician-guide-to-AndroidAPS>


Mithelfen in der Community
------------
.. toctree::
   :maxdepth: 1
   :glob:

   Wie ich helfen kann <./Getting-Started/How-can-I-help.md>
   App oder Wiki übersetzen <./translations.md>
   Am Wiki mitschreiben <./make-a-PR>


.. note:: 
	**Disclaimer und Warnung**

	* Sämtliche Informationen, Gedanken und der Quellcode sind nur für informatorische und wissenschaftliche Zwecke. Nightscout erfüllt keinerlei Anforderungen des Datenschutzes im Gesundheitswesen. Verwenden Sie Nightscout und AndroidAPS auf eigenes Risiko und setzen Sie es nicht ein, um Behandlungsentscheidungen zu treffen.

	* Bei Nutzung des Quellcodes von github.com bestehen keinerlei Gewährleistungs- und Garantieansprüche. Es gibt keinen Support. Im Übrigen wird auf die Lizenz verwiesen, die im Repository abgerufen werden kann.

	* Sämtliche Produkt- und Herstellernamen, Handelsmarken, Dienstleistungsmarken, Warenzeichen und eingetragene Dienstleistungsmarken sind Eigentum ihrer jeweiligen Inhaber und werden nur zu Informationszwecken genutzt und nicht für Werbung oder Marketing. Ihre Verwendung dient nur zur Information und bedeutet weder, dass AAPS zu ihnen gehört, noch dass sie unterstützt werden.

	Bitte beachten: Dieses Projekt steht in keinerlei Verbindung mit `SOOIL <http://www.sooil.com/eng/>`_, `Dexcom <http://www.dexcom.com/>`_, `Accu-Chek, Roche Diabetes Care <http://www.accu-chek.com/>`_ oder `Medtronic <http://www.medtronic.com/>`_
