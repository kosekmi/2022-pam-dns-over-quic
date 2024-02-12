# One to Rule them All? A First Look at DNS over QUIC

Mike Kosek | Trinh Viet Doan | Malte Granderath | Vaibhav Bajpai  
Technical University of Munich


[PAM 2022](https://pam2022.nl/), March 28&ndash;30, 2022.

[Paper Arxiv &rarr;] https://arxiv.org/abs/2202.02987

[Paper SpringerLink &rarr;] https://doi.org/10.1007/978-3-030-98785-5_24

[Dataset &rarr;] https://doi.org/10.14459/2022mp1647204

---

## Tools

The following tools were developed for our paper

1. ZMap DoQ: ZMap packet for DoQ identification (https://github.com/mgranderath/zmap-doq)
2. Verify DoQ: Verification of DoQ services (https://github.com/mgranderath/verify-doq)
3. Misc DNS Measurements: Records the negotiated DoQ as well as QUIC version and the X.509 certificate (https://github.com/mgranderath/misc-dns-measurements)
4. DNSPerf: Performance measurement library for DoQ, DoUDP, DoTCP, DoT, and DoH (https://github.com/mgranderath/dnsperf)

---

## Reproducibility

In order to enable the reproduction of our ﬁndings, we make the raw data of our measurements as well as the analysis scripts and supplementary ﬁles publicly available within this repository. Please note, that our analysis scripts use ip-api (https://ip-api.com) for IP-to-Geolocation mapping, and Caida ASRank (https://asrank.caida.org) for IP-to-AS mapping. Due to changes in IP ownership, the data derived from the APIs might change over time. For our paper, we queried the APIs on the 31.01.2022.

0. Repository Overview
* The files ```adoption.ipynb``` and ```performance.ipynb``` are the analysis scripts for the ```adoption``` and ```performance``` measurements
* The supplementary file ```Countries-Continents.csv``` is used within the analysis scripts to refine the continents of the IP-to-Gelocation mapping
* The supplementary file ```public-resolvers-ipv4s.csv``` is used within the analysis scripts to check the identified DoQ resolvers against a list of known public resolvers used in related work

1. Dataset Overview
* The dataset is provided at https://doi.org/10.14459/2022mp1647204
* The folder ```adoption.zip``` contains the DoUDP ZMap measurements from the first and the last week of the measurement study
* The folder ```misc.zip``` contains the negotiated DoQ as well as QUIC versions and the X.509 certificates of all DoQ verified resolvers during the measurement study. In addition, the databases also contain the measurement results for the ```edns-tcp-keepalive``` DNS extension, ```TCP Fast Open```, as well as ```QUIC 0-RTT```
* The folder ```performance.zip``` contains the performance measurements of our study. In addition, the database also contains the ```qlogs``` of the DoQ measurements, and the protocol-specific RTT measurements (traceroutes) using UDP, TCP, and QUIC

2. Preparations
* Clone this repository to a machine running ```Jupyter Notebook``` or ```JupyterLab```
* To minimize performance degradation through swapping, use a machine with at least 32GB of RAM
* Download the dataset (https://doi.org/10.14459/2022mp1647204) to the cloned directory switch to the cloned directory
* Extract ```adoption.zip``` to the subdirectory ```adoption/```
* Extract ```misc.zip``` to the subdirectory ```misc/```
* Extract ```performance.zip``` to the subdirectory ```performance/```

3. Adoption
* Run the Jupyter Notebook ```adoption.ipynb```

4. Performance
* Run the Jupyter Notebook ```performance.ipynb```

---

## Contact

Please feel welcome to contact the authors for further details.

* Mike Kosek (kosek@in.tum.de) (corresponding author)
* Trinh Viet Doan (doan@in.tum.de)
* Malte Granderath
* Vaibhav Bajpai (bajpai@cispa.de)
