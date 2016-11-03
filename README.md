# OOAD-WEEK11
State Diagram

##การบ้าน State Diagram

1.ATM

![](http://www.plantuml.com/plantuml/img/VP6nJWCn38PtFuNLgI2L1-Y0Mc1Xw5Ga1iIGorczg3txv3Ww8SIxanoqN1WwHVR_VOaZRw8vjTIV0Dvktt6rkiV0aTIyqzPP3v018rpyTB6qqGHpj40NQnW_0G7nVD6W56EkftFgDCbC-8vJtv3Y-ZVvaAGuk1X7qJRpk7tPzSvtWMcoUk5WKlZOoNWXSLJX0y0vBkZCNEFUP1YeVHKz1ZuiQ-_cYlWeR84J_IbULCdRDMcVPrlkN61yRibbilviuPzea1XiwxqajkpuZlmH6tTox2a2_0FgpvS77YxeV8ugcHSbpTi0-0AeDrMqAO4DSPlt_mq0)


@startuml

[*] --> insertcardatm

state "insert card to atm" as insertcardatm {

[*] --> press

press --> button.number : press your password

ATMmachine --> monitor : show password wrong

monitor --> ATMmachine : StoppedWorking(password wrong)

monitor --> ATMmachine : Continue(password correct)

monitor --> ATMmachine : Show(Main Idea)

button.number --> DepositAccount : check balances

DepositAccount --> monitor : ShowBalances

monitor --> ShowBalances

ShowBalances -->[*]

}

insertcardatm --> [*]

@enduml

---------------------------------------------------------------------------------------------------------------------------------------
2.Hospital

![](http://www.plantuml.com/plantuml/img/VO_1IWCn48RlynG_FMs5la0FfQ9GBwr2Z-9XhBDiw2PPajbg4T_TgNRRQ4K81FxvFcR-ULPEslkMwF7g2PF938keyIxcpYbRQdCLZ1OH6Z748t3-mU7zv3Uy4-wQVNORRkMDlGkiBWPwi4-2VkrOzIaBfgWED1W3Zq8OqpTru0VN3CzRCxekkg3UiXB3zJbVxxEAXoatIQm3KG5USeOrijbMjwmyh1iJNOBb-Uicllus_bk2QONQjIrSi5V7v8zD2MTjQGKBjMnmWlvWLhr_bdHV7o-X3vfBUEazVG80)



@startuml

[*] --> GotoHospital

state "Go to Hospital" as GotoHospital {

[*] -->haveaphysicalexamination

Patient --> Nurse : (have a physical examination)

Nurse --> Patient : (make appointment)

Nurse -->  AppointmentSystem  : Create

Nurse --> AppointmentSystem : Check(Data Patient)

AppointmentSystem --> Nurse : Show(Data Patient)

Nurse --> AppointmentSystem  :( fill in information)

Nurse --> MakeAppointment  : Create

Nurse -->MakeAppointment  : NumberOfPatient
} @enduml

-----------------------------------------------------------------------------------------------------------------------------------
3. Library

![](http://www.plantuml.com/plantuml/img/VOv12y8m38Nl-HN1ex0_i8DC9ep1yEP9FDGQfDYkfKc5uP-t6rE6YhUyzxwyf69HKPAp0CVr2OjYWuqNtvbpL740oB4GhXgFud5sLwXuIJt6rRmvomDJ15Y8gRLMego_OecTrpTC0U1bZV4IpypESB1g-AwPTIlaCjOo9tf3a_bPLk9MQmg2rcZgzGzwJvB1-tWuqxLt8HBpNou_IDRa4IhgByd14m00)

@startuml

[*] --> GotoLibrary

state "Go to Library" as GotoLibrary{

[*]-->LibraryUser

LibraryUser --> Catalog : Lock up

Catalog --> LibraryUser  : Display

LibraryUser --> LibraryItem : Issue

LibraryItem --> LibraryUser : Accept licence

LibraryItem --> Netserver   : Compress

LibraryItem --> Netserver  : Deliver
@endum
-----------------------------------------------------------------------------------------------------------------------------

![](http://www.plantuml.com/plantuml/img/VPBBReD034Nt_WehAr8rFy2YQbJwKXU96gLTL5qOnescdG2QCP7ozpNX8Q2eA-3wtEindjiWvAKwEe2FgqzShMvm7zW3g2wCYyGUh9339ygDOxz02jXghGHG6r2DOnrZf4niaUEM_LVXZsmmMZVA_ObpMG9C79hnmkSjvUpK_SXIVmBqcjRlo6ML8odgV0rHLnC2C2ZLO5bXF02qheeMticApGyFXN_Eoqfsbpb7ML4GhyGoljG0PXshjeTQFGUMQ1cV2clwDfkIlOwbSFQZJEQO_2nJ_v1_gSI6qj5vscV-L3skQMjZq8m6QfmTeV0h7soGoxB6wGCcuSmUoRsHg_Xlw7MNtJp7pkQrMsZN0VUbqSD6HQeNvqIfuqtwpPbCUlSxdyJiz5wqqYy0)

@startuml

[*] --> User

state "Digital Handler" as DigitalHandler

User -> DigitalHandler : action Performed (Action Event)

DigitalHandler -> KeyPanel : Get Key

KeyPanel -> Calculator : enter Digita

Calculator -> Cpu :enter Digit

Cpu -> WaitingForInputState : enter Digit(string):State

WaitingForInputState --> Cpu  : reset():void

Cpu -> OperandStack : clear():void

Cpu -> OperationStack : clear():void

Cpu -> Display: reset():void

WaitingForInputState -> Display : Add digit(string):void

Display -> Register : reset():void

Display -> DecimalValue: Add digit(string,string):string

Display -> DisplayPanel : reset(): Update(observableObject):void

DisplayPanel -> DisplayPanel : Set Display

-----------------------------------------------------------------------------------------------------------------------
![](http://www.plantuml.com/plantuml/img/ZOv12i9034NtEKNeKkW5N8XWHGikHD2Dk1XiMWQcCoL9aIBUtL4grAhWCZ_lF_vSrB2sjGCuJawOfZFSXChwt2jnQSu440abJ39RMJKEryONZZX18zXdVNG5s0inVZXmYhblMiMj4Ra4BW16mBVAZgG9NkWdl0XUERY8FazSrasU_KsFjhpU4OyU5pfwR5YHlca7r4Xw8BPbDx3UxW00)

@startuml

[*] --> LoginInterface

state "Digital Handler" as DigitalHandler{

User -> LoginInterface : Input Password

LoginInterface -> LoginInterface : Response

LoginInterface -> LoginControl : Login EmpID

LoginInterface -> LoginControl : Login Password

LoginControl -> Employee : Get EmpID

LoginControl -> LoginControl : Verify Password

}


------------------------------------------------------------------------------------------------------------------------

#Activity Diagram
1.ATM
![](http://www.plantuml.com/plantuml/img/FO_13e9034Jl_OfcJsh2Bn2GcCW1ui4RyR3kba34NR8jyVUjeFRMoPlfj62nIPRd13BAH5XU6spAwbot9u3TOOzPbgEf0rCIT3Rv3s5WLUT4p3XRvbTCtW2CFPfg8FV0oqz46IW0wgYZQ-CDpT4g814t-v-4BEyaBQG4qqHEK5LA6al1Zpt0TdJBlzl91aVyRU9fZZpAkcbfW48z-jGR)

@startuml

title ATM MACHINE

(*) --> "Insert card ATM"

--> "press password"

if "Check Password" then

-> [No] "Back to press Password"

->[true] "select order"

endif

--> "Check balances"

--> "deposit"

-->(*)

@enduml
---------------------------------------------------------------------------------------------------------------
2.open computer
![](http://www.plantuml.com/plantuml/img/JOx12eCm44Jl-OeXfrZm5ugqzAgbbnvA3q5ZNT3TacoG_ds3UF0up7l3D4bzrBpCHaddWEv-Qt6LvPirHEDE5Uhw32lZ29Uch8Ei39q2-fsfh2d4Awsa_GHAq1mPmc_OheNRqm67EGg7gXWN4TtsO1_13p-ufoSb_c2K2EAaCVTAmccZoZrZci13-Vy7)

@startuml

title OPEN Computer

(*) --> "off (shutdown the computer)"

-->[switch is turn on] "ON (turn on computer)" 

-->[switch on computer] "Boot"

--> "Ready (Waiting for instructions"

-->(*) @enduml
-------------------------------------------------------------------------------------------------------------------------------------
3.Hospital
![](http://www.plantuml.com/plantuml/img/TP3BQWCn34Nt_WgXJH_WNnWA3QNBG9QX2pVMrAAED5XAG_--zWnqqST6N7GatOiUp5Fpoxa6Pwy4--HCul2cu0hFQWjxgY7Stj_5EE5XJ6C8GxCODOUSFC6ohNN2C-1ZeTFx2X2ya0I8MQyIfwEemwmNoI-0EvKRXv8-25ZMwTTaXF3_SQf60OR3xwtDvzleawnR78fUOJToz0Xn0dpYMY4jYxBukT-q3M2ZaxPiVw5zwusVW2Jp7BQwvfrPs0eEtL_r1G00)

@startuml

title Patient go to Hospital

(*)-->"Start"

-->"insert data patient"

if "Check data" then

-down->[not found] "Don't have in database" 

-->"insert data patient"

else

if "have in database" then

-down->[yes] "Show Data"

--> "Fill appointments"

-->"records appointments"

-->"Print appointments"

endif

endif

-->"finish"

-->(*)

-------------------------------------------------------------------------------------------------------------------------------
4.scientific method
![](http://www.plantuml.com/plantuml/img/VP3FIWGn3CRlVOhGamh5DrZSW-1vcPjug3FfDjX9noPb7P_Ux1-5HHHoolVbb-Hx48rD-roSaXO4a96GbHADCAFcEZbtStSRmiPlvGqYl7SKfShUkJ3L0vkmGy7Onkn_Ea_hKZMZaFpVKsF1WJH3P7ZyMB3HRDkDJGdybcDPFn7MsXiqb5vKF1Y37OI2IQ-eO3MqZXuSG3YTjTIcv-dTPTgPY4NG08ts-JSXHLFDPe3d8HFRow-rAv3U3ss5k8_4BrU_VFF-scW6dYWvoyiiYPZac5JOMAnV)

@startuml
title  scientific method

(*)-->"Ask a question"

-down->"Research"

-down->"Hypothesis"

-down->"Hypothesis"

-down->"test with an Experiment"

if "Analyze your results" then

-left->"Hypothesis is True" 

-->"Report your Results"
 
 else
 
-right->"Hypothesis is false"

-->[Think about it/Try again]"Hypothesis"
 
else

-->"Report your Results"

endif

-->"finish"

-->(*)
------------------------------------------------------------------------------------------------------------------------------------
5.Making the tea
![](http://www.plantuml.com/plantuml/img/LK_B2i903BpdAyAULDXVg9v441zWBr9wM6bQW-kkxAOK_zvi3mKXXybaCfdiihWauzk3i7X2FBaNXm7bIIZa05QRjRMLkHMP0R1Td8BsU_OUZoIwOnRoG4vmSa99bTpZmhiy6yuZV4JsbBUcK05iuk4fjchEiVqt89y9GOytTygjqM24DJc3WDPJByNu-udgaZcZLfr6AbCA7N8FYd2ENb-k1WhKNtu0)

@startuml

title  Making the tea

(*)-->"Start"

-down->"Fill Kettle"

-down->"Heat water"

if -down->"Has the water boiles?" then

-right->[No]"Heat water"

else 

-->[Yes]"Make Tea" 

-left->"Hypothesis is True" 

end if
 
-->"STOP"

-->(*)
-------------------------------------------------------------------------------------------------------------
