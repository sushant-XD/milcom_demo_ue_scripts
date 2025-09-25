***Prerequisites:***
1) ran-tester-ue repository (latest build)

### Steps:

#### Setup:
1) Place the ue_uhd.conf and ue_uhd_alt.conf in the configs/uhd/ subdirectory of ran-tester-ue repository
2) Place the ue_parser.py in the ran-tester-ue/ directory
3) From inside the ran-tester-ue directory:
* create a virtual environment `python3 -m venv venv`
* activate the virtual environment `source venv/bin/activate`
* install all required packages `pip install -r requirements.txt`

#### Running:
1) Open three terminals 
2) On the first terminal, run rtue
3) After the UE connects to gnodeb and iperf3 server started on gnodeb side, run `ue.sh` script on another terminal. Make sure that there's traffic exchange between gNodeB and UE
4) On the third terminal, activate the virtual environment and run ue_parser.py
5) Open up the Grafana dashboard and observe the disconnection and reconnection when jamming takes place

****Note****: If the gNodeB and UE disconnect at any point because of low signal strength (instead of jamming), the AI model will still detect that as jamming and will restart the whole system.


