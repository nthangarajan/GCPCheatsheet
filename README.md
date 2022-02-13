# GCPCheatsheet

 https://console.cloud.google.com/home/dashboard


def FormatDateTimeBasedOnFacility(input_datetime : str, facility : str):
    FACILITYDATETIMEFORMAT = dict({'F 4'  : "America/Bose",
                          'F 6'  : "Manassas, Virgina",
                          'F 10' : "Asia/Singapore",
                          'F 11' : "Asia/Taoyuan",
                          'F 15' : "Hiroshima, Japan",
                          'F 16' : "Asia/Taichung"
                         }) 
    
    if (input_datetime[-1].upper() == 'Z'):
        return input_datetime
    else:
        facility = facility.strip()
        if facility in FACILITYDATETIMEFORMAT:
            return input_datetime + " " + FACILITYDATETIMEFORMAT[facility]
        else:
            print("Don't have facility in the dictionary for format")
            return input_datetime
            
def A:
    DT_FORMAT_COLUMNS = ['DT_CREATED', 'DT_INSERTED']
    
    print(FormatDateTimeBasedOnFacility('testz','Fab 16'))
print(FormatDateTimeBasedOnFacility('testZ','Fab 16'))
print(FormatDateTimeBasedOnFacility('test','Fab 16'))
print(FormatDateTimeBasedOnFacility('test','Fab 10'))
print(FormatDateTimeBasedOnFacility('test','Fab 10 '))
print(FormatDateTimeBasedOnFacility('test','Fab 45 '))
