<h3 align="center">jaunt</h3>

<p>jaunt, a GPS tracking assistant project for Computational Social Science research Center (CSSC) at hanyang university.<br>
jaunt is to gather and see people's movement data with open-source gps tracking platform, traccar, and Spacosa Gper.<br>
We are researching the difference in daily movement between the disabled people and non-disabled.</p>

## Finding Ghosts
<p>Investegating gaps between the location data. </p>

### Purpose

<p>Our participants are supposed to send their location every 60 seconds. We set up their devices and check the client working properly before experiment starts. <br>
  However, our researcher reported that Traccar sometimes sent GPS data irregularly. Some clients did not send in Traccar test data.
To catch these irregular, we are going to explorer data from our testers.<br>
  We are looking into gaps between the locations and find out about the gaps:
</p>

- The gaps mean data loss?
- If some gaps implies data loss, how can we prevent them?
- What makes the gaps? When does the gap create?
 
### Installation

 - Python 3.7 Environments. Recommand: Anaconda 2018.12 (Python 3.7 version)
 - install psycopg2 `pip install psycopg2` or `conda install psycopg2`
 - Clone the repo: `git clone https://github.com/jaehyukcha/jaunt.git`
 - Contact cssc researcher and get the `dbconfig.properties`. The data are not public for now.
 - `jupyter notebook` and open `Finding Ghosts.ipynb`
 
 
Default `dbconfig.properties` location.
```text
jaunt/
├── res/
|   └── dbconfig.properties
└────── Finding Ghosts.ipynb    
```

### See also
<p><a href="http://db.hanyang.ac.kr/doku.php?id=traccar-test-01">First report</a></p>


