# Experiment-6-Series-Queues-with-infinite-capacity--Open-Jackson-Network-
# Aim: 
To find

	a)Average number of materials in the system 
  
	b) Average number of materials in the each conveyor 
  
	c) Waiting time of each material in the system
  
	d) Waiting time of each material in each conveyor
  
If the arrival of materials follow Poisson process with the mean interval time 12 seconds, service time of lathe machine in series follow exponential distribution with service time 1 seconds, 1.5 seconds and 1.3 seconds respectively and average service time of robot is 7 seconds. 
# Software required: Visual Components and Python 
# Theory: 
An open Jackson network is a system of k service stations where station i (i = 1,2,3,…,k) has the following characteristics:
(i)  An infinite queue capacity
(ii) Customers arrive at station i from outside of the system according to a Poisson process with parameter rᵢ.
(iii) Cᵢ servers at station i with an exponential service time distribution with parameter μᵢ.
(iv) Customers completing service at station i next go to station j.
(v) Let λⱼ denote the total arrival rate of customers to station Sⱼ. Then the traffic flow equation is:
<img width="861" height="335" alt="image" src="https://github.com/user-attachments/assets/738ebddb-78ac-486a-b7c5-606ee3beb094" />
# Program 
~~~
Name: YUVASREE S
Ref no: 25014102
Slot no:3P1-1

arr_time=float(input("Enter the mean inter arrival time of objects from feeder (in secs):")) 
ser_time1=float(input("Enter the mean inter service time of lathe machine 1 (in secs):")) 
ser_time2=float(input("Enter the mean inter service time of lathe machine 2 (in secs):")) 
ser_time3=float(input("Enter the mean inter service time of lathe machine 3 (in secs):")) 
Robot_time=float(input("Enter the Additional time taken for the robot (in secs):")) 
lam=1/arr_time 
mu1=1/(ser_time1+Robot_time) 
mu2=1/(ser_time2+Robot_time) 
mu3=1/(ser_time3+Robot_time) 
print("---------------------------------------------") 
print("Series Queues with infinite capacity-Open Jackson Network") 
print("----------------------------------------------") 
if(lam<mu1) and (lam<mu2) and (lam<mu3): 
    Ls1=lam/(mu1-lam) 
    Ls2=lam/(mu2-lam) 
    Ls3=lam/(mu3-lam) 
    Ls=Ls1+Ls2+Ls3 
    Lq1=Ls1-lam/mu1 
    Lq2=Ls2-lam/mu2 
    Lq3=Ls3-lam/mu3 
    Wq1=Lq1/lam 
    Wq2=Lq2/lam 
    Wq3=Lq3/lam 
    Ws=Ls/(3*lam) 
    print("Average number of objects in the system S1: %0.2f"%Ls1) 
    print("Average number of objects in the system S2: %0.2f"%Ls2) 
    print("Average number of objects in the system S3: %0.2f"%Ls3) 
    print("Average number of objects in the over all system : %0.2f"%Ls) 
    print("Average number of objects in the conveyor S1: %0.2f"%Lq1) 
    print("Average number of objects in the conveyor S1: %0.2f"%Lq1) 
    print("Average number of objects in the conveyor S2: %0.2f"%Lq2) 
    print("Average number of objects in the conveyor S3: %0.2f"%Lq3) 
    print("Average waiting time of an object in the system S1: %0.2f secs"%Wq1) 
    print("Average waiting time of an object in the system S2: %0.2f secs"%Wq2) 
    print("Average waiting time of an object in the system S3: %0.2f secs"%Wq3) 
else: 
    print("Warning! Objects overflow will happen in the conveyor") 
print("--------------------------------------------------------------")
https://colab.research.google.com/drive/1G5EJsabnl1h_g0P2l4oReq8AObWd_JZ1#scrollTo=N5_aencMiRYi
~~~

# Output
~~~
Enter the mean inter arrival time of objects from feeder (in secs):12
Enter the mean inter service time of lathe machine 1 (in secs):1
Enter the mean inter service time of lathe machine 2 (in secs):1.5
Enter the mean inter service time of lathe machine 3 (in secs):1.3
Enter the Additional time taken for the robot (in secs):7
---------------------------------------------
Series Queues with infinite capacity-Open Jackson Network
----------------------------------------------
Average number of objects in the system S1: 2.00
Average number of objects in the system S2: 2.43
Average number of objects in the system S3: 2.24
Average number of objects in the over all system : 6.67
Average number of objects in the conveyor S1: 1.33
Average number of objects in the conveyor S1: 1.33
Average number of objects in the conveyor S2: 1.72
Average number of objects in the conveyor S3: 1.55
Average waiting time of an object in the system S1: 16.00 secs
Average waiting time of an object in the system S2: 20.64 secs
Average waiting time of an object in the system S3: 18.62 secs
--------------------------------------------------------------
~~~

# Result

  The average number of material in the system and in the conveyor and waiting time are successfully found. 
