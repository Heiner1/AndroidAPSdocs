# Bomba Accu-Check Insight

**Este software é parte de uma solução DIY (faça você mesmo) e não é um produto, no entanto é necessário que VOCÊ leia, aprenda e compreenda o sistema, incluindo a forma de o usar. Não é algo que faz a gestão total da sua diabetes, mas permite melhorá-la, bem como a sua qualidade de vida se estiver disposto a dar-lhe o tempo necessário para isso. Não tenha demasiada pressa, permita-se ter tempo para aprender. Você é o responsável como utiliza e configura o sistema.**

* * *

## ***AVISO:** Se você tem usado o Insight com **SightRemote** anterior, por favor **atualize para a versão 2.1** e **desinstale o SightRemote**.*

## Requisitos de hardware e software

* Uma bomba Insight Roche Accu-Chek (qualquer firmware, todos funcionam) <br /> Nota: AAPS irá escrever os dados sempre no **primeiro perfil de taxa basal na bomba **
* Um telefone Android (basicamente todas as versões Android funcionariam, mas o próprio AndroidAPS requer pelo menos o Android 5 (Lollipop).)
* O AndroidAPS (pelo menos a v2.1) instalado no seu telefone

## Instalação

* The Insight pump should only be connected to one device at a time. If you have previously used the Insight remote control (meter), you must remove the meter from the paired devices list of your pump: Menu > Settings > Communication > Remove device
    
    ![Screenshot of Remove Meter Insight](../images/Insight_RemoveMeter.png)

* In [Config builder](../Configuration/Config-Builder) of the AndroidAPS app select Accu-Chek Insight in the pump section
    
    ![Screenshot of Config Builder Insight](../images/Insight_ConfigBuilder.png)

* Toque no ícone de configuração (catraca) para abrir as configurações Insigth.

* In settings, tap on the button 'Insight pairing' at the top of the screen. You should see a list of all nearby bluetooth devices (below left).
* On the Insight pump, go to Menu > Settings > Communication > Add Device. The pump will display the following screen (below right) showing the serial number of the pump.
    
    ![Screenshot of Insight Pairing 1](../images/Insight_Pairing1.png)

* Going back to your phone, tap on the pump serial number in the list of bluetooth devices. Then tap on Pair to confirm.
    
    ![Screenshot of Insight Pairing 2](../images/Insight_Pairing2.png)

* Both the pump and phone will then display a code. Check that the codes are the same on both devices and confirm on both the pump and the phone.
    
    ![Screenshot of Insight Pairing 3](../images/Insight_Pairing3.png)

* Success! Pat yourself on the back for successfully pairing your pump with AndroidAPS.
    
    ![Screenshot of Insight Pairing 4](../images/Insight_Pairing4.png)

* To check all is well, go back to Config builder in AndroidAPS and tap on the cog-wheel by the Insight Pump to get into Insight settings, then tap on Insight Pairing and you will see some information about the pump:
    
    ![Screenshot of Insight Pairing Information](../images/Insight_PairingInformation.png)

Note: There will be no permanent connection between pump and phone. A connection will only be established if neccessary (i.e. setting temporary basal rate, giving bolus, reading pump history...). Otherwise battery of phone and pump would drain way too fast.

## Settings in AAPS

![Screenshot of Insight Settings](../images/Insight_pairing.png)

In the Insight settings in AndroidAPS you can enable the following options:

* "Log site changes": This will automatically record an insulin cartridge change when you run the "fill cannula" program on the pump.  
    <font color="red">Note: A cannula change also resets Autosens</b></font>
* "Log tube changes": This adds a note to the AndroidAPS database when you run the "tube filling" program on the pump.
* "Log battery changes": This records a battery change when you put a new battery in the pump.
* "Log operating mode changes": This inserts a note in the AndroidAPS database whenever you start, stop or pause the pump.
* "Log alerts": This records a note in the AndroidAPS database whenever the pump issues an alert (except reminders, bolus and TBR cancellation - those are not recorded).
* "Enable TBR emulation": The Insight pump can only issue temporary basal rates (TBRs) up to 250%. To get round this restriction, TBR emulation will instruct the pump to deliver an extended bolus for the extra insulin if you request a TBR of more than 250%.  
    <font color="red">Note: Just use one extended bolus at a time as multiple extended boluses at the same time might cause errors.</font>
* "Recovery duration": This defines how long AndroidAPS will wait before trying again after a failed connection attempt. You can choose from 0 to 20 seconds. If you experience connection problems, choose a longer wait time.   
      
    Example for min. recovery duration = 5 and max. recovery duration = 20   
      
    no connection -> wait **5** sec.   
    retry -> no connection -> wait **6** sec.   
    retry -> no connection -> wait **7** sec.   
    retry -> no connection -> wait **8** sec.   
    ...   
    retry -> no connection -> wait **20** sec.   
    retry -> no connection -> wait **20** sec.   
    ...

* "Disconnect delay": This defines how long (in seconds) AndroidAPS will wait to disconnect from the pump after an operation is finished. Default value is 5 seconds.

For periods when pump was stopped AAPS will log a temp. basal rate with 0%.

In AndroidAPS, the Accu-Chek Insight tab shows the current status of the pump and has two buttons:

* "Refresh": Refreshes pump status
* "Enable/Disable TBR over notification": A standard Insight pump emits an alarm when a TBR is finished. This button lets you enable or disable this alarm without the need for configuration software.
    
    ![Screenshot of Insight Status](../images/Insight_Status2.png)

## Settings in the pump

Configure alarms in the pump as follows:

* Menu > Settings > Device settings > Mode settings > Quiet > Signal > Sound Menu > Settings > Device settings > Mode settings > Quiet > Volume > 0 (remove all bars)
* Menu > Modes > Signal mode > Quiet

This will silence all alarms from the pump, allowing AndroidAPS to decide if an alarm is relevant to you. If AndroidAPS does not acknowledge an alarm, its volume will increase (first beep, then vibration).

Insight pumps with newer firmware will vibrate briefly every time a bolus is delivered (for example, when AndroidAPS issues an SMB or TBR emulation delivers an extended bolus). Vibration cannot be disabled. Older pumps do not vibrate in these circumstances.

## Battery replacement

The Insight pump has a small internal battery to keep essential functions like the clock running while you are changing the removable battery. If changing the battery takes too long, this internal battery may run out of power, the clock will reset, and you will be asked to enter a new time and date after inserting a new battery. If this happens, all entries in AndroidAPS prior to the battery change will no longer be included in calculations as the correct time cannot be identified properly.

## Insight specific errors

### Extended bolus

Just use one extended bolus at a time as multiple extended boluses at the same time might cause errors.

### Time out

Sometimes it might happen that the Insight pump does not answer during connection setup. In this case AAPS will display the following message: "Timeout during handshake - reset bluetooth".

![Insight Reset Bluetooth](../images/Insight_ResetBT.png)

In this case turn off bluetooth on pump AND smartphone for about 10 seconds and then turn it back on.

## Crossing time zones with Insight pump

For information on traveling accross time zones see section [Timezone traveling with pumps](../Usage/Timezone-traveling#insight).