# SMS Commands

### Workaround for bug in AndroidAPS 2.3

SMS Command Settings are disabled in AndroidAPS versions 2.3 because of a bug, but can be used in version 2.4 again.

If you must use SMS commands you can use the following workaround:
* Export settings
* Downgrade to AndroidAPS version 2.2 (by installing your version 2.2 APK-file)
* Do SMS command settings in AndroidAPS version 2.2.
* Upgrade to AndroidAPS 2.3. SMS command settings will not be accessible there.


## Safety First

* AndroidAPS allows you to control a child's phone remotely via text message. If you enable this SMS Communicator, always remember that the phone set up to give remote commands could be stolen. So always protect it at least by a PIN code.
* AndroidAPS will also inform you by text message if your remote commands, such as a bolus or a profile change, have been carried out. It is advisable to set this up so that confirmation texts are sent to at least two different phone numbers in case one of the receiving phones is stolen.

## How it works

In your android phone setting go to Applications > AndroidAPS > Permissions and enable SMS

In AndroidAPS go to Preferences > SMS Communicator and enter the phone number(s) that you will allow SMS commands to come from (separated by semicolons, no spaces or other characters anywhere - i.e. +4412345678;+4412345679) and also enable 'Allow remote commands via SMS'.

Send a SMS to the phone with AndroidAPS running from your approved phone number(s) using any of the commands below in **bold**, the phone will respond to confirm success of command or status requested.

**Hint**: It can be useful to have SMS flat for both phones if a lot of SMS will be sent.

## BG
- Last BG: 5.6 4min ago, Delta: -0,2 mmol, IOB: 0.20U (Bolus: 0.10U Basal: 0.10U)
## LOOP STOP/DISABLE
- Loop has been disabled
## LOOP START/ENABLE
- Loop has been enabled
## LOOP STATUS
- Loop is disabled
- Loop is enabled
- Suspended (10 min)
## LOOP SUSPEND 20
- Loop suspended for 20 minutes
## LOOP RESUME
- Loop resumed
## TREATMENTS REFRESH
- TERATMENTS REFRESH 1 receivers
## NSCLIENT RESTART
- NSCLIENT RESTART 1 receivers
## PUMP
- Last conn: 1 minago Temp: 0.00U/h @11:38 5/30min IOB: 0.5U Reserv: 34U Batt: 100
## BASAL STOP/CANCEL
- To stop temp basal reply with code EmF
## BASAL 0.3
- To start basal 0.3U/h for 30 min reply with code Swe
## BASAL 0.3 20
- To start basal 0.3U/h for 20 min reply with code Swe
## BASAL 30%
- To start basal 30% for 30 min reply with code Swe
## BASAL 30% 50
- To start basal 30% for 50 min reply with code Swe
## BOLUS 1.2
- To deliver bolus 1.2U reply with code Rrt
- Remote bolus not allowed (_if within 15 min after last bolus command or remote commands not allowed_)
## EXTENDED STOP/CANCEL
- To stop extended bolus reply with code EmF
## EXTENDED 2 120
- To start extended bolus 2U for 120 min reply with code EmF
## CAL 5.6
- To send calibration 5.6 reply with code Rrt
- Calibration sent (_if xDrip is installed. Accepting calibrations must be enabled in xDrip+_)
## PROFILE STATUS
- Profile1
## PROFILE LIST
- 1.`Profile1` 2.`Profile2`
## PROFILE 1
- To switch profile to Profile1 100% reply with code Any
## PROFILE 2 30
- To switch profile to Profile2 30% reply with code Any



