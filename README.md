# KYRenewableHAFetch
This is a demonstration of an integration for Home Assistant to fetch Kentucky real-time renewable integration data from a local utility.  This uses REST to fetch the data from a JSON file through a web address and then present it to Home Assistant as readable "sensors".   

## Background
A utility serving Kentucky has solar, wind, and hydroelectric generation resources.  Real-time data on the production from these resources is available through a web-accessed JSON file.  
This small integration uses REST to read the JSON file (with default scan interval of 20 seconds) and present the resource data as "sensors" that can then be used in automations in Home Assistant. 
This integration was initially developed at the University of Kentucky by Larry Holloway with assistance from Juan Valencia.  This integration is being shared through GitHub to make it easy to share and replicate among the research team.  (Yes, many parts of the integration are very simple, but sharing it via a gitHub package will simplify distribution among the team and will reduce the need of users to reinvent YAML code.) 

NOTE:  At this time, the web address for the real-time JSON file is left blank in this integration installation, pending permission from the utility to make it widely public.  After installing this integration, the user will have to set the web address. 

NOTE: These files all pertain to a particular setup of devices.  Any user will not have the same devices with the same device ids or automation ids. This code is primarily meant to document the basic code that can be used and modified by other researchers. 

##  Expected format of the JSON file
The file at the minimum will have a "Time" field, a "Solar Generation (%)" field, a "Wind Generation (%)" field, and a "Hydro Generation (%)" field.  An example of the file, with just the required lines, is shown below: 

[ \
&ensp;{ \
&ensp;&ensp;"Time": "2026-08-28 21:54:37",\
&ensp;&ensp;"Solar Generation (%)": 15.1,\
&ensp;&ensp;"Wind Generation (%)": 9.1,\
&ensp;&ensp;"Hydro Generation (%)": 0,\
&ensp;}\
]


