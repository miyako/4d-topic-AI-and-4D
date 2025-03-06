# 4d-topic-AI-and-4D

notes from [4D Method User Group Meeting #77](https://4dmethod.com/2025/02/27/4d-and-ai-bring-the-power-of-llms-to-your-4d-applications-ricardo-mello/)

## The Qodly Demo

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
  * **Note**: the menu item is titled  "Web Studio…" in 4D 20 LTS. the item does not appear if a valid *4D Developer Professional* licence is not installed
 
* click "Data"

<img src="https://github.com/user-attachments/assets/1d8cff1b-ddb6-40e2-82e3-f2c5d3e2e983" width=250 height=auto />

* Data Explorer is displayed

<img src="https://github.com/user-attachments/assets/55dad93d-6f3f-4698-9601-39520bb57125" width=500 height=auto />

* return to Qodly Studio
* find "Preview in studio" tool

<img src="https://github.com/user-attachments/assets/05479fcb-88ef-4b2f-8d33-09710e5c6ae5" width=500 height=auto />

* this is different from the "run" tool which has an ominous warning messsage "The Server and Client app Schemes don't match".

<img src="https://github.com/user-attachments/assets/257bcf57-2fc3-4e88-ad5d-b0612750d68d" width=500 height=auto />

* if you click on the "run" tool, you will be warned about the descrepancy. but more importantly, any attempt to access data will systematically fail because there are no previligies defined in *roles.json* and `ds.authentify()` is not implemented in the application.

<img src="https://github.com/user-attachments/assets/694da473-d421-4432-b8cb-3d91aac82612" width=250 height=auto />

* the "Preview in studio" tool is part of the studio and has access to data **without authentication**.
* type in the prompt ""show me all invoices for hiroshi". you should get an error. this is because the API key to call groq is not set in code.
 
<img src="https://github.com/user-attachments/assets/095d281e-c6ed-4054-bfc9-05acfabb8b71" width=500 height=auto />

* in 4D, paste the API keys in place of the string `<add your key here>`

<img src="https://github.com/user-attachments/assets/f57b9641-2a65-49d1-997d-daf67ee53877" width=500 height=auto />

* notice the warning in line `10`. evidently this part is unfinished.

> The function or property generateText does not exist on type cs.GroqHandler. (550.2) 

<img src="https://github.com/user-attachments/assets/ed7c77c9-1c41-4a89-92de-e99c7d94b85e" width=500 height=auto />

* try again. this time a valid JSON is returned from groq but unlike the demo no data is found.

<img src="https://github.com/user-attachments/assets/2118e16a-b968-499c-88f0-5635a38a7214" width=500 height=auto />

* the same query works with other common western names

<img src="https://github.com/user-attachments/assets/d3299b19-8431-4611-bed1-a87b54d43c16" width=500 height=auto />

* so you can guess that a more explict prompt e.g. "show me all invoices for a person whose name is "hiroshi"" would have a better chance.

<img src="https://github.com/user-attachments/assets/a9dc6e6f-57b8-450b-896c-0af8d50d34f1" width=500 height=auto />

* to go deeper, place a break point in line `33` of `cs.GroqHandler.generateData()`
* run the earlier query. you will see that groq has inferred that "hiroshi" is likely a last name, not a first name.

<img src="https://github.com/user-attachments/assets/a0273544-7fba-4dff-88c6-22289758284d" width=500 height=auto />

* maybe you can add a computed attribute to search for either names. just a thought.

* the page is designed to display a list of contacts and their invoices, as opposed to a list of invoices and their contacts. so the list of invoices is populated in this example but not the list of contacts. it was like this in the demo. the components are independent and either one is used to display a list of invoices or contacts as a collection.

* now try "show me all contacts whose age > 30"

<img src="https://github.com/user-attachments/assets/ce82c11a-fb61-488e-bf46-532855fcc260" width=500 height=auto />

* also try "show me all contacts who is about to turn 30"

<img src="https://github.com/user-attachments/assets/ad61b8ac-be18-4f15-ac15-59a622103661" width=500 height=auto />
