<h3 align="center">jaunt</h3>

jaunt, a GPS tracking assistant project for Computational Social Science research Center (CSSC) at hanyang university.
jaunt is to gather and see people's movement data with open-source gps tracking platform, traccar, and Spacosa Gper.
We are researching the difference in daily movement between the disabled people and non-disabled.

## Finding Ghosts
We are collecting our participant's location data via Traccar client. It should be send its location every 60 seconds. Actually, it sends <b>ALMOST 60 seconds</b> because there is a few seconds of delay.

After several experiments, we have found some gaps much longer than we expected --a minute and few seconds-- between the location data. There is over than 10 minutes even a few hours gaps are existed. We could many missing data if the participant moved around with inactive Traccar client. This can make serious distortion of the data and harm our trust in Traccar.


## Purpose

<p>Our participants are supposed to send their location every 60 seconds. We set up their devices and check the client working properly before experiment starts. <br>
  However, our researcher reported that Traccar sometimes sent GPS data irregularly. Some clients did not send in Traccar test data.
To catch these irregular, we are going to explorer data from our testers.<br>
  We are looking into gaps between the locations and find out about the gaps:
</p>

1. What makes the gaps? When does the gap create?
2. The gaps mean data loss?
3. If some gaps implies data loss, how can we prevent them?

 
## Installation


Our reference DB is postgresql. If you have any Traccar data your own (like csv), there is no necessary libraries to run the code here beyond the Anaconda distribution of Python The code should run with no issues using Python versions 3.*.
But, you have to install `psycopg2` if you want to connect postgresql DB or run the notebook as is.

 - install psycopg2 `pip install psycopg2` or `conda install psycopg2`
 
and db connection profile need to be place as below.

Default `dbconfig.properties` location.
```text
jaunt/
├── res/
|   └── dbconfig.properties
└────── Finding Ghosts.ipynb    
```

## File Descriptions

Finding Ghosts.ipynb: A notebook contains process of connting DB (without connection info), inspection of Traccar location data, and calculation of gaps between location data. Following markdown cells leads to group the gap which has some interval in the number of minutes.


## Results
<a href="http://db.hanyang.ac.kr/doku.php?id=traccar-test-01">First report</a>


We found about the gaps as below:

1. These are make the gaps: Sleep/idle mode of the device, Traccar blocked by OS, and Low battery.
2. The gaps doesn't always mean data loss. Most gaps caused by sleep/idle mode of the device and it doesn't make any data loss. However, some gaps by low battery or blocking background process can cause serious data loss.
3. To prevent low battery situations, we should monitoring participant's battery level and notify him when it's getting low. <br>
   It is not certain how to prevent blocked client. We can just wait until iPhone blocks Traccar and allow again. It seems to pick Traccar out from energy saving process in Samsung's Android phones.

## Licensing, Authors, Acknowledgements

Our location data are closed for now. Otherwise, the code can be used without any limitations.
    
Authors: 
Main author and editor: Jaehyuk Cha (chajh@hanyang.ac.kr)
DB Managing and Technical support: Geunseong Jung (aninteger@hanyang.ac.kr)

This work was supported by the National Research Foundation of Korea(NRF) grant funded by the Korea government(*MSIT) (No.2018R1A5A7059549). *Ministry of Science and ICT.


