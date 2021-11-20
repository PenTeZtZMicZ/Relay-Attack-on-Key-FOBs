---


```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
# **Key FOB Relay Attack**
#### *By: PenTeZtZMicZ* ####
***
<p align="center">
    <img width="40%" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.xautoworld.com%2Fwp-content%2Fuploads%2F2018%2F12%2Fmodel-s-being-stolen-featured-700x321.jpg&f=1&nofb=1">
  </p>




## **Context** 
***
Earlier in the term, I was in an interview, tasked with the challenge of describing how to hack into a car via its key fob. This was a new concept for me, so I did some extensive research after the interview to learn wireless penetration testing for a car, to develop an in-depth understanding. Therefore this post is a summation of my key findings, based upon the minimal information public on this topic. 


<div style="margin-bottom:4em;">



## **What Is A Relay Attack?** 
***
A relay attack is an exploitation which enables the attacker to gain access to a vulnerable vehicle, avoiding tamper detection and alarms, whilst preventing physical damage. The attacker will analyse and capture the frequency of a key FOB whilst the victim is opening their vehicle, utilizing a Software Designed Radio receiver and transceiver (SDR). This  signal will then be re-transmitted (relayed), on command to unlock the vehicle. This example is also commonly paired with a garage door, as it can also be exploited via this way.


  <p align="center">
    <img width="40%" src="https://www.lufsec.com/wp-content/uploads/2018/10/squematic.png">
    <figcaption> <p align="center"> This is a diagram highlighting the physical hardware and its relation to unlocking a vehicle via a car key FOB.</p></figcaption>
  </p>

<div style="margin-bottom:4em;">

## **Relay Attack**
***
### *What tools are required to capture and relay the signal from the key fob?*
<p>A SDR such as:</p> 
* **HackRf**: This tool is capable of reception and transmission of radio signals from 1MHZ - 6MHZ.
  + To achieve this, the HackRF has an antenna which is able to intercept the signal.
  
  <p align="center">
  <img width="40%" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.makerlab-electronics.com%2Fwp-content%2Fuploads%2F2018%2F03%2FHackRF-One-07.jpg&f=1&nofb=1">
</p>
  


  
<div style="margin-bottom:2em;">

### *What type of key FOBs are susceptible to this kind of attack?*
Original car key FOBs used a static token which was transmitted to the vehicle to unlock it. These legacy key FOBs are still used by the public, creating perceived risk to the  vehicle. 


Manufacturers are now integrating new systems which utilize rolling codes, creating a new code after each code request is made. This system has mitigated the original attack on car key FOBs, however, are still vulnerable to other common exploitations such as jamming or brute-force attacks. 

<div style="margin-bottom:2em;">
  
  
### *How to do conduct the attack?*
*This attack will be described with the example of using the HackRf.* 

**Step 1:** Find and set the tool to the frequency in which the key FOB is operating at to enable the capturing of the token. This can be analysed via researching via the FOB's ID or by using a spectrum analysis tool to detect frequencies in real-time. <br>
**Step 2:** Press the key FOB and record its signal. (Since the HackRF is now configured to the correct frequency, the token will be visible in real-time via the visualizer when pressed) <br>
**Step 3:** Transmit the radio signal received to unlock the desired vehicle. <br>


<div style="margin-bottom:4em;">


## **Mitigation Strategies**
***
Companies such as Upstream Security have implemented cloud security software (UpStream C4 platform) within the car that utilities artificial intelligence to track and learn the user's behavioral data (for example it documents digital signatures produced by the OBD port). This system will then use this data in presence of an anomaly detected, analyzing it parallel to the model's data to detect and prevent malicious activity. This solution works via an SOC which means the complete process is not entirely automated, therefore deriving concerns around real-time perceived threat management. This solution will also need to be heavily regulated, tracking and accessing user vehicle data, posing potential ethical concerns. Therefore, transparency towards the consumer is key for this solution's success.



Subsequently, car key FOBS in its current state will require the constant research and design, working together with cyber security professionals to further improve its security whilst wireless access is becoming the norm to present/near future automobiles.



<div style="margin-bottom:4em;">


## **Authors Note**
***
* I would preferably like to demonstrate these findings practically within this post however these tools are a. difficult to obtain or b. very expensive, with the HackRF costing $300.
* Currently there is very little information made public regarding this kind of attack, potentially due to the perceived risk of criminal behaviour.

<div style="margin-bottom:8em;">

## **References**
***

<a href="https://cybersecurity-excellence-awards.com/candidates/upstream-c4-centralized-connected-car-cybersecurity-platfom/">UpStream C4 </a> <br>
<a href="https://cybersecurity-excellence-awards.com/candidates/upstream-c4-centralized-connected-car-cybersecurity-platfom/">How to Mitigate Keyless Entry Attacks</a> <br>
<a href="https://upstream.auto/solutions/vehicle-soc/">UpStream C4 vehicle solutions</a> <br>
<a href="https://www.lufsec.com/hacking-car-key-fobs-with-sdr/">Hacking Car Key Fobs with SDR</a> <br>





