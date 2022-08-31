# Common call control 

the purpose of the common call control is  receive the request and then have to handling the protocol to specific  controllers(HYYP, Diameter, FTP, etc.).
Common call controller will become interfaces with the others parts of the system 

## Subscriber Model

subscriber model is related to the information of the subscriber(Device, User, Account, Group)  
* **Group:** is a particular combination of a package of a group  
* **User:** is an entity which gives an idea what is the user information are (email, notification via SMS, or Email)

## Service Model

Service model is something related to service, for charging/rating entities, it dose all the computation using the common call control model information 

## Session Management

## Charging & Rating

## Life Cycle

Life Cycle model is something to cover cyclic availability, ex: if I subscribe to monthly 10Gb package, the package will be available every month (will renew it every month), not one month. 
so that renewable information  and how much to renew either its weekly or monthly, it all goose in the life cyclic information map 


## EDR/CDR

### <span style="color:green">E</span>vent <span style="color:green">D</span>etail <span style="color:green">R</span>ecord
### <span style="color:green">C</span>all <span style="color:green">D</span>etail <span style="color:green">R</span>ecord
EDR/CDR something related to detail record. 
so when we have call related information, event happening   it goose to CDR 
if there is prevising related information(create a device, tariff) 


## Audit


# Call Control Function 

when we receive a diameter CCR request,  the call controller first received the subscription-id(my device ex: my mobile number), so the call controller will git that in the request and send it to subscriber model to determined that the device exists or not, if it exists it will send the request to the charging module


# SPS Charging 
* SPS charging is primely responsible for online rating and charging for the data sessions.
* as well as it also provide what ever the request that is coming from Gy interface it provides a balance management and session management.
* it also applicable for SMS and MMS and another customer type.
* it also involves ART rules or we can say the rule engine which is well come across when ever using the charging  allot, rule engine is a window gived to customer to change something,



![[Pasted image 20220823164636.png]] 



![[Pasted image 20220823164653.png]]


when a device by a bundle( bundle is a package, ex 10GB package) an instance of this bundle is created so called a <span style="color:green;font-weight:bold">Subscription</span> instance, how buys the subscription is the **<span style="color:green;font-weight:bold">Account</span> 


in the **<span style="color:green;font-weight:bold">Bundle</span>** definition we have a **<span style="color:red;font-weight:bold">Charging Service</span>**  is the one which determines what to be charged it can be a bucket, main balance or counter 

<span style="color:green;font-weight:bold">Bucket</span> is additional balance from my account main balance

<span style="color:green;font-weight:bold">Tariff</span> is where we specify that is it a home or is it a rooming for example, condition based to charge from the specific bucket 


<span style="color:green;font-weight:bold">Rate</span> is amount of charge you want to specify, it is entity which we specify that for example for one minute we will charge 2$

<span style="color:green;font-weight:bold">Threshold</span> is entity that after consumption of the bucket what I should do ex: limit the data speed to 2Kps and notify  the customer that he reached the limit of the bucket 

# SPS Data Entity Relationships
![[Pasted image 20220824092127.png]]

# Charging Modes


in general there tree types of event happening:
* Immediate Event Charging(IEC) Immediate Debit, when I send  SMS it will check if there is enough balance or not, a single charging request which either succeeds or fails 
  ![[Pasted image 20220824093649.png]]


*  Two step Debit on charging or diameter (ECUR), the first stage is a reservation of the cost amount, the second one is the commitment of this amount.  
  
![[Pasted image 20220824095240.png]]

* Session Charging with Unit Reservation(SCUR), is also named as Quoted-based Charging, Two Step charging with reservation-Update and terminate.
  
![[Pasted image 20220824100351.png]]


# Charging Engine

![[Pasted image 20220824100827.png]]

