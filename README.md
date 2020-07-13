# Battery-Indicator-for-Laptop

Code :-

import win10toast;import time;import psutil;import pkg_resources.py2_warn
def update():
    global battery;global plugins;global battery_percentage
    battery=psutil.sensors_battery();plugins=battery.power_plugged;battery_percentage=str(battery.percent)
    return battery,battery_percentage
def condn():
    while True:
        update()
        if plugins==True:
            loop()
        for i in range(len(battery_status)):
            if battery_percentage==battery_status[i]:
                notification.show_toast("Battery Notification","Battery is "+battery_percentage+"%",icon_path="battery_indicator.ico")
                if plugins == True:
                    notification.show_toast("Battery Notification","Charger Connected Successfully\n""Battery is "+battery_percentage+"%",icon_path="battery_indicator.ico")
                loop()
def loop():
    for i in range(len(battery_status)):
        update();time.sleep(0.2)
        while battery_percentage==battery_status[i] or plugins==True:
            update();time.sleep(0.8)
            if plugins==True:
                notification.show_toast("Battery Notification","Charger Connected\n""Battery is "+battery_percentage+"%",icon_path="battery_indicator.ico");time.sleep(0.5)
                while plugins==True:
                    update();time.sleep(0.5)
                    if plugins==False :
                        notification.show_toast("Battery Notification","Charger Disonnected\n""Battery is "+battery_percentage+"%",icon_path="battery_indicator.ico")
                        condn()
if __name__ == "__main__" :
    update();notification = win10toast.ToastNotifier()
    battery_status = ["5","15","30","90","100"]
    notification.show_toast("Battery Notification","Battery is "+battery_percentage+"%",icon_path="battery_indicator.ico")
    condn()


