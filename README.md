# Battery-Indicator-for-Laptop

Required modules :- 
 win10toast ( used to give notification)
 psutil ( gives current values battery status and percentage)
 pkg_resources.py2_warn ( required during making .exe file)
 pyinstaller (to make .exe file of python file)
 
 To make .exe file :- In Command prompt , go to file location and type 
 pyinstaller --onefile -w filename.py
 
Specification :- 
  1. Notify at 5 , 15 , 30 ,90 , 100 percent battery.
  2. Notify about battery connection status
