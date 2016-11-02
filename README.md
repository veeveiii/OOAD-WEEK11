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
} @endum

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

4.

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

----------------------------------------------------------------------------------------------------------------------
5.
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
