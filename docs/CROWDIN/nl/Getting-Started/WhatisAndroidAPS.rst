What is a closed loop system with AndroidAPS?
****************************

AndroidAPS is a app that acts as an artificial pancreas system (APS) on an Android smartphone. What is an artificial pancreas system? It is a software program that aims to do what a living pancreas does: keep blood sugar levels within healthy limits automatically. 

An APS can't do the job as well as a biological pancreas does, but it can make type 1 diabetes easier to manage using devices that are commercially available and software that is simple and safe. Those devices include a continuous glucose monitor (CGM) to tell AndroidAPS about your blood sugar levels and an insulin pump which AndroidAPS controls to deliver appropriate doses of insulin. The app communicates with those devices via bluetooth. It makes its dosing calculations using an algorithm, or set of rules, developed for another artificial pancreas system, called OpenAPS, which has thousands of users and has accumulated millions of hours of use. 

A note of caution: AndroidAPS is not regulated by any medical authority in any country. Using AndroidAPS is essentially carrying out a medical experiment on yourself. Setting up the system requires determination and technical knowledge. If you don't have the technical know-how at the beginning, you will by the end. All the information you need can be found in these documents, elsewhere online, or from others who have already done it -- you can ask them in Facebook groups or other forums. Many people have successfully built AndroidAPS and are now using it entirely safely, but it is essential that every user:

* Builds the system themselves so that they thoroughly understand how it works
* Adjusts its individual dosage algorithm with his or her diabetes team to work nearly perfect
* Maintains and monitors the system to ensure it is working properly

.. note:: 
	**Disclaimer en waarschuwing**

	* Alle informatie, gedachten, en de code die hier beschreven staan zijn alleen voor informatieve en educatieve doeleinden. Nightscout probeert zich op geen enkele wijze te houden aan gegevensbewaking van medische gegevens. Gebruik van Nightscout en AndroidAPS is op eigen risico, en gebruik de informatie of code niet om behandelbeslissingen te nemen.

	* Het gebruik van code van github.com is zonder enige garantie of formele ondersteuning. Verdere details zijn te vinden in de licentie, die te vinden is in de Repository op github.

	* Alle product-en bedrijfsnamen, handelsmerken, servicemerken, geregistreerde handelsmerken en geregistreerde dienstmerken zijn eigendom van hun respectievelijke houders. Hun gebruik is voor informatieve doeleinden en impliceert op geen enkele wijze een samenwerking met of goedkeuring van hen.

	Please note - this project has no association with and is not endorsed by: `SOOIL <http://www.sooil.com/eng/>`_, `Dexcom <http://www.dexcom.com/>`_, `Accu-Chek, Roche Diabetes Care <http://www.accu-chek.com/>`_ or `Medtronic <http://www.medtronic.com/>`_.
	
If you're ready for the challenge, please read on. 

Primary goals behind AndroidAPS
===========================================

* An app with safety built in. To read about the safety features of the algorithms, known as oref0 and oref1, click here (https://openaps.org/reference-design/)
* An all-in-one app for managing type 1 diabetes with an artificial pancreas and Nightscout
* An app to which users can easily add or remove modules as needed
* An app with different versions for specific locations and languages.
* An app which can be used in open- and closed-loop mode
* An app that is totally transparent: users can input parameters, see results, and make the final decision
* An app which is independent of particular pump drivers and contains a "virtual pump" so users can safely experiment before using it on themselves 
* An app closely integrated with Nightscout
* An app in which the user is in control of safety constraints 

How to start
===============
Of course, all of this content here is very important, but can be in the beginning quite confusing.
A good orientation is given by the `Module Overview <../Module/module.html>`_ and the `Objectives <../Usage/Objectives.html>`_. You can also take a look on the `sample setup with Dana, Dexcom and Sony Smartwatch <../Getting-Started/Sample-Setup.html>`_.
 
