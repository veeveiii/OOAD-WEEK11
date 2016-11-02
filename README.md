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
------------------------------------------------------------------------------------------------------------------------

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
}

@endum

-----------------------------------------------------------------------------------------------------------------------------------
