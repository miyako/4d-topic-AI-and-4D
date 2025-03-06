# 4d-topic-AI-and-4D

* goto https://groq.com/
* create an account with email
* check inbox
<img src="https://github.com/user-attachments/assets/67038dab-8bdf-4e1d-a860-ec29c17d5481" width=500 height=auto />

* goto [API Keys](https://console.groq.com/keys)
* click "Create API Key" and create a private API key for the demo application

<img src="https://github.com/user-attachments/assets/57586462-701e-4022-ba5c-b8e2bcf8b7a7" width=500 height=auto />

* goto https://github.com/rmello4d/AI-4dmethod
* fork repository or download zip
* unarchive `AI-4dmethod-main.zip`
* unarchive `AIDemo4Dmethod.zip`
* delete preferences folders
  * userPreferences.pc
  * userPreferences.Wakanda 2.0
* delete other detritus
  * Project/DerivedData
* open `AIDemo.4DProject` with latest 4D 20 Feature Request (R8 100240 as of today) 
* when asked to specify data file click "Open" and select data file
  * Data/AIDemo.4DD
* goto File > Web Administration > Settings…

<img src="https://github.com/user-attachments/assets/c360291a-4951-4128-8430-739e45b55ea6" width=500 height=auto />

* click "Reset to factory settings"

<img src="https://github.com/user-attachments/assets/0ae368e5-1313-4215-b3ab-034a0a8fb266" width=500 height=auto />

* activate "Launch WebAdmin server at startup"
* activate "Enable access to Qodly Studio"
* click "Define (Access key)"
* enter secret string

<img src="https://github.com/user-attachments/assets/807a4e42-49b2-4451-993b-0fc71272e009" width=300 height=auto />

* click "OK" and restart interpreted

<img src="https://github.com/user-attachments/assets/20c881c4-ee63-4f39-bb4f-108649cb1e71" width=500 height=auto />

* on Mac, goto "System Settings > Desktop and Dock" and change the default browser to [Chrome, Edge or Firefox](https://developer.4d.com/docs/WebServer/qodly-studio)
* goto Design > Qodly Studio…  
  * **Note**: the menu item is title  "Web Studio…" in 4D 20 LTS. the item does not appear if a valid *4D Developer Professional* licence is not installed
* in Qodly Studio, find the "run" tool in "Explorer > Pages > demo"
  * there is an ominous warning messsage "The Server and Client app Schemes don't match"
<img src="https://github.com/user-attachments/assets/79409240-7e12-4a15-a22e-15cb94f5e329" width=500 height=auto />

* click the button anyway

<img src="https://github.com/user-attachments/assets/694da473-d421-4432-b8cb-3d91aac82612" width=250 height=auto />

* the page seems to render but there is an error and a warning in the console
 
<img src="https://github.com/user-attachments/assets/d5214216-da19-4fbf-b7c6-fdfc1f5cf7d8" width=500 height=auto />

* error `:8080/web.ico:1`
> Failed to load resource: the server responded with a status of 404 (Not Found)
* warning `components.js?t=1741242656512:1`
> Unsatisfied version 0.3.67 from @qodly/studio of shared singleton module @ws-ui/webform-editor (required =0.3.28)


  
