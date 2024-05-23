#  Cloud_Computing_ESE
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/ESE_Notes.git)

# Table of Contents
1. [Previous Years Questions](#previous-year-questions)
2. [WSDL, SOAP and EDI](#ppt-12)
3. [SLA & Types of SLA](#ppt-14)
4. [RDBMS, File System Layer, GFS, HDFS](#ppt-16)
5. [MapReduce, Parallel Computing](#ppt-17)
6. [SLA based questions](#ppt-18)
7. [Resource Management](#ppt-19)
8. [CC Economic Viewpoint](#ppt-20)
9. [Resouce management challenges](#ppt-21) 
10. [Green Cloud & Data Centers](#ppt-22)



## Previous Year Questions

Q1. a. **Differentiate between web service SLA and Cloud SLA. (At least 4 points).**

Ans. 
| **Criteria**               | **Web Service SLA**                                     | **Cloud SLA**                                              |
|----------------------------|---------------------------------------------------------|------------------------------------------------------------|
| **Scope of Services**      | Specific web service (API, web app)  [ SaaS and PaaS]                    | Broad range of cloud services (compute, storage, etc.) [IaaS]   |
| **Performance Metrics**    | API response time, error rates, transaction throughput  | VM uptime, storage I/O, database availability, network latency |
| **Responsibility and Control** | Full control by service provider                      | Shared responsibility between provider and customer        |
| **Outage and Compensation**| Credits/refunds for specific service downtime           | Complex service credits for various cloud services         |

**![](https://lh7-us.googleusercontent.com/MNdViozfNs4b0lpC-aWLWHAJ90cuy12ZW_-m045oK4MhPxUWirqDCJOIlhy2Li8MKGrkKpXOhLcBwhisE6QzzJZi0b1T6owkD4zYU6uzDUVrXe9Y4TdyGUvX9HD3FRSRKk7qcBxNGqokZt5QYDv_3HM)**nb 
<hr>

Q1. b. **What is the need of Universal Description Discover and Integration
(UDDI)? Demonstrate UDDI in detail.**

Ans. 
- This is a registry service. So that the metadata information can be saved and provided to the customers
- A framework to define XML-based registries.
- Registries are repositories that contain documents that describe business data and also provide search capabilities and programmatic access to remote applications.
- Businesses can publish information about themselves and the services they offer.
- Can be interrogated by SOAP messages and provides access to WSDL documents describing web services in its directory.

- *Service Registry*:
	- Provides support for publishing and locating services.
	- Like telephone yellow pages.
- *Service Provider*:
	- Provides e-business services.
	- Publishes these services through a registry.
- *Service Requestor*:
	- Finds required services via the service broker.
	- Binds to services via Service Provider.


**![](https://lh7-us.googleusercontent.com/SdG8y2T5jwKpIqXYTLJAl22kqVOGvQR_gSrJ5HsP0AKz_07IdtOmN4Oeyu57dMSb16sP1Efz0CVgxDdrAOUKpAIAuDCim7XLQJ8h6bPTKs_Sbf7V5Baj0dvfWSJKW9Y1fyV1BiW1ZkmknOdz1JN1ydQ)**
<hr>

Q1. c. **Consider the peak computing demand for an organization is 200 units. The demand as a function of time can be expressed as: <br>$D(t) = 25\sin(t)$ 0 <= t <π/2 <br>$D(t) = 45\sin(t)$ π/2 <= 1 <π <br>The resource provisioned by the cloud to satisfy the current demand at time t is given as:<br>$R(t) = D(t) + \delta \frac{d(D(t))}{dt}$<br>Where, δ is the delay in provisioning the extra computing resource on demand. The cost to provision unit cloud resource for unit time is 0.9 units. <br> Calculate the penalty. (Assume the delay in provisioning is π/9 time units and the minimum demand is 0.)**

Ans. 

To calculate the penalty, we need to determine the extra resource provisioned due to the delay in provisioning. The delay ($\delta$) is given as $\pi/9$ time units. We will use the provided demand functions, differentiate them to find the rate of change of demand, and then compute the total provisioned resources over the given time periods.

Given:
$D(t) = 25\sin(t)$ for $0 \leq t < \frac{\pi}{2}$
$D(t) = 45\sin(t)$ for $\frac{\pi}{2} \leq t < \pi$

The resource provisioned by the cloud is:
$R(t) = D(t) + \delta \frac{d(D(t))}{dt}$
Where $\delta = \frac{\pi}{9}$.

First, let's calculate $\frac{d(D(t))}{dt}$:

For $0 \leq t < \frac{\pi}{2}$:
$D(t) = 25\sin(t)$
$\frac{d(D(t))}{dt} = 25\cos(t)$

For $\frac{\pi}{2} \leq t < \pi$:
$D(t) = 45\sin(t)$
$\frac{d(D(t))}{dt} = 45\cos(t)$

Next, let's find $R(t)$:

For $0 \leq t < \frac{\pi}{2}$:
$R(t) = 25\sin(t) + \frac{\pi}{9} \cdot 25\cos(t)$
$R(t) = 25(\sin(t) + \frac{\pi}{9}\cos(t))$

For $\frac{\pi}{2} \leq t < \pi$:
$R(t) = 45\sin(t) + \frac{\pi}{9} \cdot 45\cos(t)$
$R(t) = 45(\sin(t) + \frac{\pi}{9}\cos(t))$

Now, we need to calculate the cost of provisioning the extra resource. <br>
The penalty is the cost of provisioning the resources due to the delay. <br> We need to integrate $R(t)$ over the given time periods and then calculate the cost.

**Integrate $R(t)$ over the intervals:**

For $0 \leq t < \frac{\pi}{2}$:

$\int_0^{\frac{\pi}{2}} R(t) \, dt = \int_0^{\frac{\pi}{2}} 25(\sin(t) + \frac{\pi}{9}\cos(t)) \, dt$

$= 25 \int_0^{\frac{\pi}{2}} \sin(t) \, dt + 25 \cdot \frac{\pi}{9} \int_0^{\frac{\pi}{2}} \cos(t) \, dt$

$= 25 \left[ -\cos(t) \right]_0^{\frac{\pi}{2}} + 25 \cdot \frac{\pi}{9} \left[ \sin(t) \right]_0^{\frac{\pi}{2}}$

$= 25 \left( -\cos\left(\frac{\pi}{2}\right) + \cos(0) \right) + 25 \cdot \frac{\pi}{9} \left( \sin\left(\frac{\pi}{2}\right) - \sin(0) \right)$
$= 25 \left( -0 + 1 \right) + 25 \cdot \frac{\pi}{9} \left( 1 - 0 \right)$
$= 25 + 25 \cdot \frac{\pi}{9}$
$= 25 + \frac{25\pi}{9}$

For $\frac{\pi}{2} \leq t < \pi$:

$\int_{\frac{\pi}{2}}^{\pi} R(t) \, dt = 
\int_{\frac{\pi}{2}}^{\pi} 45(\sin(t) + \frac{\pi}{9}\cos(t)) \ dt$

$= 45 \int_{\frac{\pi}{2}}^{\pi} \sin(t) \, dt + 45 \cdot \frac{\pi}{9} \int_{\frac{\pi}{2}}^{\pi} \cos(t) \ dt$

**![](https://lh7-us.googleusercontent.com/jMPRFxENrRxd7iyTxO6K9-yxFAIDLfmFc1rnEH9ZWpz_Ntszcqo-ipg6__Du2VU1nJXq4MSuRX2-R0nLS30sBhknL04S3RbjCG67Gdnl_NipjRHV_ERbjpDGo-4SkubxyvaeJVjZSqjbB4zpoqQJhVA)**

$= 45 \left( -\cos(\pi) + \cos\left(\frac{\pi}{2}\right) \right) + 45 \cdot \frac{\pi}{9} \left( \sin(\pi) - \sin\left(\frac{\pi}{2}\right) \right)$

$= 45 \left( -(-1) + 0 \right) + 45 \cdot \frac{\pi}{9} \left( 0 - 1 \right)$

$= 45 \left( 1 \right) + 45 \cdot \frac{\pi}{9} \left( -1 \right)$

$= 45 - \frac{45\pi}{9}$

$= 45 - 5\pi$

**Total Provisioned Resources:**
$\text{Total Provisioned} = \left( 25 + \frac{25\pi}{9} \right) + \left( 45 - 5\pi \right)$

$= 25 + \frac{25\pi}{9} + 45 - 5\pi$

$= 70 + \frac{25\pi}{9} - \frac{45\pi}{9}$

$= 70 - \frac{20\pi}{9}$

**Calculate the Penalty**
$\text{Penalty Cost} = \int_0^{t}[D(t) - R(t)]\times \text{Cost of provisioning 1 unit}$

$= |70 - (70 - \frac{20\pi}{9})\times 0.9|$

$=\frac{20\pi}{9} \times 0.9$

$Penalty = 2\pi = 6.28$

<hr>

Q1. d. **Suppose a cloud guarantees a service availability for 99% of time <br> Let a third party application runs in the cloud for I0 hours/day. <br>At the end of one month, it was found that total outage is 9.25 hours. <br> Find out whether the provider has violated the initial availability
guarantee.**

Ans. 


Let's calculate the values to determine the outcome.

Given:
- Guaranteed availability: $99\% = 0.99$
- Total time/day: $10$ hours
- Total days in a month: $30$
- Total outage over one month: $9.25$ hours

### Step 1: Calculate total amount of uptime in the month

$\text{Uptime} =\text{Total hours served in the month} - \text{Total outage}$
$= 300 - 9.25$
$= 290.75$

Therefore the percentage of service availability is  :
= $\frac{290.75}{300}\times{100}$
= $96.9166\%$

and 
$96.9166 \% < 99\%$

So they violated the initial availability guarantee

<hr>

Q2. a. **Consider the peak computing demand for an organization is 500 units. The demand as a function of time can be expressed as <br>$D(t)=80(1+e^{-t})$ <br>Baseline (owned) unit cost is 320 and cloud unit cost is 400. <br>In this situation is cloud cheaper than owning for a period of 500 time units?**

Ans. 

To determine whether the cloud is cheaper than owning for a period of 500 time units, we need to calculate the total cost of owning and the total cost of using the cloud over this period.

### Cost of Owning (Baseline):
The cost of owning is calculated based on the baseline (owned) unit cost multiplied by the peak computing demand.

Baseline Cost = Baseline Unit Cost × Peak Computing Demand × Time units

$\text {Baseline Cost} = 320 × 500 × 500 = ₹8,00,00,000$


### Cost of Cloud Usage:
The cost of cloud usage depends on the demand function $D(t)$, the cloud unit cost, and the time period.

Given:
- Cloud unit cost: ₹400
- Demand function: $D(t) = 80(1 + e^{-t})$

To find the total cost of cloud usage over a period of 500 time units, we need to integrate the demand function over this period and multiply it by the cloud unit cost.

Total Cloud Cost = $\int_{0}^{500} D(t) \, dt \times \text{Cloud Unit Cost}$

We'll calculate this integral:

$D(t) = 80(1 + e^{-t}) ×400$

$\int_{0}^{500} D(t) \, dt = 80 \int_{0}^{500} (1 + e^{-t}) \, dt ×400$

$= 80 \left[ t - e^{-t} \right]_{0}^{500}×400$

$= 80 \left[ (500 - e^{-500}) - (0 - e^0) \right]×400$

$= 80 \left[ 500 - e^{-500} + 1 \right]×400$

$= 80 \left[ 501 - e^{-500} \right]×400$

Now, let's calculate this value:

$= 32000 \times (501 - e^{-500})$

$=32000 \times (501−e^{−500})$

$≈32000 \times(501−0)≈80×(501−0)$ (since $e^{−500}$ is extremely close to 0)

$=32000 \times {501}$

$=₹1,60,32,000$

### Compare Costs:
Utility ( U ) = $\frac{C_t}{B_t}$

= $\frac{₹1,60,32,000}{₹8,00,00,000}$
= $0.2004$

Since the Cost of cloud is almost $\frac{1}{5}$ times lesser than the in-house, it is cheaper

<hr>

Q2. b. **What is map-reduce? Appy to the following word-count problem with the input: <br>Fl: The store opens in the morning. <br>F2: The store opens at 9am.**

Ans.
 
**MapReduce :**
MapReduce is a programming model and framework for processing and generating large datasets in parallel across a distributed cluster of computers. It consists of two main phases: the map phase and the reduce phase.

In the map phase, input data is divided into smaller chunks and processed independently by multiple worker nodes. Each worker node applies a function (the "map" function) to the input data, producing intermediate key-value pairs.

In the reduce phase, the intermediate key-value pairs produced by the map phase are shuffled and sorted based on their keys. Then, the reducer function is applied to each unique key, consolidating and aggregating the values associated with that key.

**Mapper Output:**
-  The - 1 
- store - 1 
- opens - 1 
- in - 1 
- the - 1 
- morning - 1 
- The - 1 
- store - 1
-  opens - 1
-  at - 1 
- 9am - 1 

 **Reducer Output**: 
 - The - 2 
 - store - 2
 -  opens - 2
 -  in - 1
 -  the - 1
 -  morning - 1
 -  at - 1
 -  9am - 1

<hr>

Q2. c. **Discuss Google File System (GFS). <br>In a map reduce framework consider the HDFS block size is 256MB. We have 3 files of size 128KB, 258MB, and 260MB. <br>How many blocks will be created by Hadoop framework?**

Ans. 
### GFS Architecture ( Google File System )
* A single master controls the file namespace
* Large files are broken up into chunks (GFS) or blocks (HDFS)
* Typical size of each chunk: 64 MB
* Stored on commodity (tinux) servers called Chunk servers (GFS) or Data nodes (HDFS)

Replicated three times on different:
- Physical rack
- Network segment

There are various functions in GFS, namely :

1. Read Operation
-Client program sends the full path to the **Master** ( GFS ) or **Name Node** ( HDFS )
- Master replies with the meta data of a chunk where this data is found
- Client reads the data from the designated chunk server


2. Write and Append Operation
- Client program sends the full path to the **Master** ( GFS ) or **Name Node** ( HDFS )
- Client sends data in the form of chunks to the chunk servers ( whose meta data is provided ) for the data to be appended.
- The chunks of data are replicated to multiple chunk servers for fault tolerance
- The master server updates the metadata of the chunk servers

3. Fault Tolerance
- Master maintains regular communication with the chunk servers
- In case of failure : 
	- The chunk server meta data reflects the failure
	- The master assigns a new primary server from the replicates if a primary server has failed
4. Big Table
- It is a distributed storage system on which GFS is built
- Data is accessed by use of 
	- Row-key
	- Column-key
	- Timestamps
5. Big Table Storage
- Each table is split into different row ranges, called tablets 
- Each tablet is managed by a tablet server
- Supports large parallell reads


>Example : Dynamo
>- Developed by amazon
>- Supports large volume of concurrent updates, each of which should be small in size.

Given : 
- HDFS block size is 256MB. 
- We have 3 files of size 128KB, 258MB, and 260MB. 

Therefore number of blocks made by hadoop = 
$128KB = 1$
$258MB = 2$
$260MB = 2$
$Total = 5$

And 
$Replicas = 5\times 3 = 15 \text {blocks}$ 


<hr>

### MapReduce based questions
Q2. d. **Apply map reduce to the following word-count problem, with the
input: <br> Fl: Cheer, Fear, Rear <br> F2: Cycle, Cycle, Rear <br> F3: Cheer, Cycle, Fear**

Ans. 

### Input:
- F1: Cheer, Fear, Rear
- F2: Cycle, Cycle, Rear
- F3: Cheer, Cycle, Fear

#### mapper.py
```python
def mapper(file_content):
    # Split the file content into lines
    for line in file_content:
        # Split each line into words
        words = line.strip().split(", ")
        # Emit key-value pairs
        for word in words:
            emit(word, 1)

```

#### reducer.py 
```python
def reducer(mapped_data):
    word_count = {}
    # Iterate over the mapped data
    for word, count in mapped_data:
        if word in word_count:
            word_count[word] += count
        else:
            word_count[word] = count
    # Emit the final counts
    for word, count in word_count.items():
        emit(word, count)

```

### Map Phase:
For each input file, we tokenize the lines into words, count the occurrences of each word in the file, and emit key-value pairs:

For F1:
- (Cheer, 1)
- (Fear, 1)
- (Rear, 1)

For F2:
- (Cycle, 1)   # Cycle appears twice
- (Rear, 1)

For F3:
- (Cheer, 1)
- (Cycle, 1)
- (Fear, 1)

### Shuffle and Sort Phase:
After shuffling and sorting by key, we gather all values for each unique word:

- (Cheer, [1, 1])
- (Cycle, [2, 1])
- (Fear, [1, 1])
- (Rear, [1, 1])

### Reduce Phase:
For each unique word, sum up the counts:

- Cheer: 1 + 1 = 2
- Cycle: 2 + 1 = 3
- Fear: 1 + 1 = 2
- Rear: 1 + 1 = 2

### Output:
The final output will be the word counts:

- Cheer: 2
- Cycle: 3
- Fear: 2
- Rear: 2

### Corrected Final Output:
```python
{
  'Cheer': 2,
  'Cycle': 3,
  'Fear': 2,
  'Rear': 2
}
```
<hr>

Q3. a. **What is service level agreement (SLA)? What are the different key performance indicators? Describe in brief.**

Ans.
- Whenever the service provider and the service consumer want to exchange the services there must exist some agreement.
- Agreement involves pricing, service availability factor and other quality factors such as reliability, performance, security.
- SLA is a formal contract between a service provider (SP) and a service consumer (SC). and it is a foundation of the consumer's trust in the provider.

Example :If the uptime is 95%, then there must be guarantee that the Cloud Provider will maintain that guarantee

**Key Performance Indicators**
- Low-level resource metrics and directly measured from the system.
- Multiple KPIs are composed, aggregated or converted to higher SLOS
- Example: downtime, uptime, inbytes, outbytes, packet size etc.
- Possible mappimg: Availability(A)=1-(downtime/uptime)
- Monitoring
	- Natural questions
	- Solution: neutral third party organization to perform monitoring
	- Eliminates conflict of interests
- Auditibility: consumer requirement

Metrics for monitoring and auditing : 
- Throughput
- Availability
- Reliability
- Load balancing
- Durability
- Elasticity
- Linearity
- Agility
- Automation
- Customer service response time
- Service level violation rate
- Transaction time and resolution time

<hr>

Q3. b.**Illustrate web service model With diagram.**

Ans.
**Roles in web service architecture**: 
1.  **Service provider**: 
- Owner of the  service and provides a platform that hosts use to access the service.
2. **Service requestor**: 
- It is usually a business or individual that requires certain functions to be satisfied. 
- It initiates a request to the service registry to discover and obtain information about the services
3. **Service Registry**: 
- Searchable registry of service descriptions here service providers publish their service descriptions.

**![](https://lh7-us.googleusercontent.com/mooPdlMIMWbPu2hBtzWSPm-lsnpUNCLeKk4ddqI4CmVrNMl9DcsgxAPEB1Zq0tVXx0qX5GQGQhp8XczZ261lg8Lih3IUxVHdJxMfwxlUHwEe5xVLm3R-jjrneJkyELFaV1Zx3Y6HQ42dPj-48IsHycU)**

<hr>

Q3. c. **What is the motivation for sensor cloud computing? Illustrate
sensor cloud in detail.**

Ans.
#### Motivation for Sensor Cloud Computing
- Increasing adoption of sensing technologies (e g.RFID . cameras, mobile phones)
- Internet has become a source ot real time informatim (eg., through blogs, social networks, forums) for events happening around us
- Cloud computng has emerged as an attractive solution for dealing with the 'Big Data' revolution.
By combinng data obtaned from sensors with that from the
intenet, we can potentially create a demand for resources that can be appropriately met by the cloud.
**![](https://lh7-us.googleusercontent.com/O0QyPTOipFOoQXMLc7FhgW7dpwQWdKfA_hA54EhNovc62kdfp_wOkxwUIDw20LHpdw4ZLi7LyC11zsf0tckNsuWVlETC-EzwCsF0tEQNFAXc3IraXT9_hOdFu4nwIRnTRpjYI_SDsMoRMwQxkWUkwe8)**

<hr>

Q3. d. **Write the pseudo-codes (for map and reduce functions) for
calculating the average of a set of integers in MapReduce. <br> Suppose A= (15, 25, 35, 45, 55, 65, 75) is a set of integers. Take 4 mapper nodes and 1 reducer node. <br> Show the map and reduce outputs.**

Ans.
$A = (15, 25, 35, 45, 55, 65, 75 )$
> A contains 7 elements

Mapper Nodes = 4
| Mapper | Numbers | Avg | Count |
|--|--|--|--|
|$M_1$| 15, 25 | 20 | 2 |
|$M_2$| 35, 45 | 40 | 2 |
|$M_3$| 55, 65 | 60 | 2 |
|$M_4$| 75 | 75 | 1 |
|Sum | 315 | 195 | 7 |

```
avg = [20, 40, 60, 75 ]
arr = [(15, 25), (35, 45), (55, 65), 75 ] 
```
Reducer Node : 1
$Avg\times Count$ 
1. $20\times 2 = 40$
2. $40 \times 2 = 80$
3. $60\times 2 = 120$
4. $75\times 1 = 75$

$\frac{Sum}{Total count} = \frac{40 + 80 + 120 + 75}{2+2+2+1}$

$\Sigma{Sum} = 315$

$\Sigma{Count} = 7$

$Average = 45$

#### Pseudocode :
##### Mapper.py :
```python
def map(arr)
	sum = 0;
	for i in range (0, len(arr)) :
		sum = sum + arr[i]
avg_mapper = (sum*1.0)/len(arr)
print(avg_mapper, len(arr))
# Pass it to the reducer
``` 


##### Reducer.py
```python
def reduce (avg, arr)
	sum = count = 0
	for i in range (0, len(arr)) :
		sum = sum + avg[i]*len(arr[i])
		count = count + len(arr[i])
	average = (sum*1.0)/count
print (average)
```

<hr>

Q4. a. **Discuss various Parallell DB architectures with detailed diagrams**

Ans. 

#### Parallel DB Architectures : 
- **Shared memory**
	- Suitable for servers with multiple CPUs.
	- Memory address space is shared and managed by a symmetric multi-processing (SMP) operating system.
	- SMP schedules processes in parallel exploiting all the
processors.
- **Shared Nothing**
	- Cluster of independent servers each with its own disk space.
	- Connected by a network.
- **Shared Disk**
	- Hybrid Architecture
	- Independent server clusters share storage through high speed network storage viz. Network attached storage (NAS) or SAN (Storage Area Network).
	- Clusters are connected to the storage via: standard ethernet or
faster fiber channel or Infiniband connections.

**![](https://lh7-us.googleusercontent.com/9aUAjBrPrEeCT9lK74R8n1AVmPS4jmlE3Mp07b_dgWsQt_tf3dr9d8aTZLVD9TkFlz2Y0it7p4wxJJyk49XFHY0GvX33Wjb7G7kudL5MMRnQYv_NeP58nnBZcjjVSHuWhrzvrk68VoW3hBRJmvkX_5M)**
<hr>

Q4. b **Describe Openstack Cloud Architecture and its key components.**

Ans.
OpenStack is a cloud operating system that controls large pools of compute, storage, and networking resources throughout a datacenter, all managed through a dashboard that gives administrators control while empowering their users to provision resources through a web interface.

It has SaaS, IaaS and PaaS capabilities

#### Major Openstack Components : 
*Service - Compute
Project- Nova*
- Manages the lifecycle of compute instances in an OpenStack environment. 
- Responsibilities include spawning, scheduling and decommissioning of virtual machines on demand.

*Service - Networking
Project- Neutron*
- Enables Network-Connectivity-as-a-Semce for other OpenStack services, such as OpenStack Compute.

*Service - Object storage
Project - Swift*
- Stores and retrieves arbitrary unstructured data objects via a RESTfuI, HTTP based API.

*Service- Block storage
Project- Cinder*
- Provides persistent block storage to running instances.

*Service - Identity
Project - Keystone*
- Provides an authentication and authorization service for other OpenStack services.
- Provides a catalog of endpoints for all OpenStack services.

*Service - Image service
Project - Glance*
- Stores and retrieves virtual machine disk images.

*Service - Telemetry
Project - Ceilometer*
- Monitors and meters the OpenStack cloud for billing, benchmarking, scalability, and statistical purposes.

*Service - Dashboard
Project - Horizon*
- Provides a web-based self-service portal to interact with underlying
OpenStack services. 

**![](https://lh7-us.googleusercontent.com/Xo5p6qgjOzx6xMAYoHMbLrY5iOiKaboB69vpqAOuC8X-_EK55G3u867cHhP2J8pfT24oqWlbDuOxnYqq74ldy1c0qUk13vQXgJJwdV7LOq-ggFNOAsS9zw_hxVOj57S7hr5rkY8ZHPyeeJn-vV_om0w)**
**![](https://lh7-us.googleusercontent.com/FLfd8sWgHhqfTsGNkINsSi-LOXHEt2JyhEWJysJwEhgzzelQqsw77pVBpPD8RnshwrP0YDtSDRZ7CoVjOKDYZU3_BW0NDsC7Db9xZU4nxeatsEH0hWGdDvpLSlau-VvyCk8NtU_Bcp8KgBD_Lx5sKzY)**
<hr>

Q4. c. **Write pseudo codes for computing total and calculate average salary of on organization ABC while grouping them by Gender (male or female) using MapReduce. The input is as follows: <br> Name, Gender. Salary <br>Sam, M, 10000 <br>Shalini, F, 15000**

Ans. 
#### Pseudocode 
##### Mapper.py
```python
import sys
import as

for line in sys.stdin
	line = line.strip()
	line = line.split(",")

	name = line [0]
	gender = line[1]
	sal = line[2]
	print "%s, %d" % (gender, int(sal))
# instead of a print statement 
# we can assume this to be a 
# return statment to the reducer function
	

```
```
M 10000
M 15000
F 15000
```


##### Reducer.py
```python
import sys
dictOrg = {}

for line in sys.stdin :
	line = line.strip()
	gender = line[0]
	sal = line[1]
	
	if gender in dictOrg :
		dictOrg[gender].append(int(sal))
	else :
		dictOrg[gender] = []
		dictOrg[gender].append(int(sal))

for gender in dictOrg.keys() : 
	Total_sal = sum(dictOrg[gender[]])
	sal_avg = Total_sal/len(dictOrg[gender])
	
print ("%s, %d, %d" % ( gender, Total_sal, sal_avg ))

```
<hr>

## Availability question 
Q4. d. **In a cloud service uptime is 300 minutes and downtime is 30
minutes. What is the availability of service ?**

Ans.
To calculate the availability of a cloud service, we use the formula:

$\text{Availability} = \frac{\text{Uptime}}{\text{Total Time}} \times 100\%$

Given:
- Uptime = 300 minutes
- Downtime = 30 minutes

First, we calculate the total time:
$\text{Total Time} = \text{Uptime} + \text{Downtime} = 300 + 30 = 330$ minutes

Now, we can calculate the availability:
$\text{Availability} = \frac{300}{330} \times 100\%$

Let's compute this:

$\text{Availability} = \frac{300}{330} \times 100$
$\text{Availability} = \left( \frac{300}{330} \right) \times 100$
$\text{Availability} \approx 90.91\%$

Therefore, the availability of the service is approximately $90.91\%$.

<hr>
 
### Cloud and In house server comparision

Q5. a. **A company Y needs to support a spike in demand when it becomes popular followed potentially by a reduction once some of the visitors turn away. The company has two options to satisfy the requitements which are given in the following table :**
| Expenditures | In-House server | Cloud server|
|--|--|--|
|Purchase Cost| 1100000| No cost|
|Number of CPU Cores| 17|13|
| Cost / hour( Over 3 year span ) | No cost | 47 |
|Efficiency | 50% ( underutilized ) | 90% |
|Power and Cooling ( Cost / hour ) | 27 | - | 
|Management Cost | 11 | 6 | 

1. **Calculate the price of a core-hour on in-house server and cloud server.**
2. **Find the  effective  cost /hour for both the options.**
3. **Calculate the ratio of the total cost/effective hour for in house to cloud deployment**
4. **If the efficiency of in house server is increased to 72% which deployment will have now better total cost / effective hour?**

Ans. 
#### Core/Hour cost

$\text{Cost / hour} = \frac{\text {Purchase cost }}{\text {Total time}}$

$\text{Core / hour cost} = \frac{\text {cost / hour}}{\text {no. of cores}}$


$\therefore \text{in-house cost / hour} = \frac{11,00,000}{365 \times 3 \times 24} = ₹41.86$

$\text{In house core / hour cost} = \frac{41.86} {17} = ₹2.46$

$\text{Cloud core / hour cost} = \frac{47}{13} = ₹3.61$

#### Effective cost

$\text{Cost / effective hour} = \frac{\text {cost /hour }}{\text {efficiency}}$

$\text{In house cost / effective hour} = \frac{41.86}{0.5} = ₹83.72$

$\text{Cloud cost / effective hour} = \frac{47}{0.9} = ₹52.22$

#### Total cost/ effective hour

$\text{Total Cost / effective hour} = \text{cost / effective hour} + \text{power and cooling cost} + \text{management cost}$

$\text{Total In-house Cost / effective hour} = 83.72 + 27 + 11 = ₹121.72$

$\text{Total Cloud Cost / effective hour} = 52.22 + 6 = ₹58.22$

#### New effective cost / hour
$\text{In house cost / effective hour} = \frac{41.86}{0.72} = ₹58.13$

$\therefore \text{ The in house will now have a better deployment as compared to the cloud server, based on cost/ effective hour }$

<hr>

Q5. b. **Consider a scenario where a company Y wants to use a cloud service from a provider P. The service level agreement (SLA) guarantees negotiated between the two parties prior to initiating the business are as follows: <br> Avaialbility guarantee 99.95% time over the service period.<br> Service period: 31 days <br> Max service hours per day: 8 hours <br> Cost: Rs. 70/- per day <br> Service credits are awarded to customers if availability guarantees are not satisfied. Monthly connectivity uptime service level are given as:**
|Monthly uptime connectivity (%)| Service credit|
|--|--|
|<99.95%|20%|
|<99%|25%|
**However, in reality it was found that over the service period, the cloud service suffered 7 outages of the duration: <br> 5 hrs, 20min, 2 hr 20 min, 20min, 3hrs 25 min. 35min, 2 hr, each on different days, due to which normal service guarantees were violated.  <br> If SLA negotiation are honoured, compute the effective cost payable towards buying the cloud service.**

Ans.
$\text{Service per day} = 8 hours$
$\text{Total hours } = 31\times8$
$= 248 hours$


But based on outages to the total amount of actual uptime is  : 
$\text{Actual Uptime} = 234 hours$
$\text{Total Downtime} = 14hours$

$\text{Availability} = \frac{\text{Uptime}}{\text{Total Time}} \times 100\%$
$\therefore\text{Availability} = \frac{234}{248} \times 100\%$
 
$\text{Availability} =94.3548\%$

& $94.3548\% < 99%$

$\therefore \text{Service Credit} = 25% \times \text{Ideal Payable}$
$=\frac{25}{100} \times 2170\% = ₹542.5$

So, $\text{ Total Payable} =  2170 - 542.5 = ₹1627.5$


<hr> 

Q5. c. **What is the motivation behind Green cloud computing? Explain green cloud computing in detail.**

Ans. 
#### Green Computing
- Green computing is the environmentally responsible and eco-friendly use of computers and their resources.
- In broader terms, itis also defined as the study of designing, manufacturing or engineering, using and disposing of computing devices in a way that reduces their environmental impact
- Green Cloud computing is envisioned to achieve not only efficient processing and utilization of computing infrastructure, but also minimize energy consumption.

- Green computing consist of advanced scheduling schemas to reduce energy consumption.
- This could mean being aware about two things :
	- Power 
	- Thermal output
- Performance/Wattage is or isnot following Moore' s law.
- In such applications we have data centers, which are designed to reduce power usage effectiveness.
	- Cooling systems
	- Rack design

<br> 

## PPT 12
Q1.**What is WSDL ?  Describe the Document structure of a WSDL document**

Ans.
#### WSDL ( Web Services Description Language )
- It is an XML vocabulary standard for describing web services and their capabilities. 
- It is a contract between the XML web service and the client.
- Specifies what a request message must contain and what the response message will look like in unambiguous notation.
- Defines where the service is available and what communications protocol is used to talk to the service.
- A WSDL document is just a simple XML document.
- It defines a web service using these major elements
	- **Port type**: The operations performed by the web service.
	- **Message**: The messages used by the web service
	- **Types**: The data types used by the web service
	- **Binding**: The communication protocols used by the web service.

Example : 

```
<message name="creditRequest"> 
	<part name="customerID" type="xsd:string"/> 
</message> 
<message name="creditResponse"> 
	<part name="creditResult" type="xsd:string"/> 
</message> 
.
.
.
<portType name="CheckCredibility"> 
	<operation name="checkCredit"> 
		<input message="tns: creditRequest"/> 
		<output message="tns: creditResponse"/> 
	</operation> 
</portType
```

<hr>

Q2. **What is SOAP ? What are it's building blocks and message structure ? What are it's characteristics ?**

Ans. 
#### SOAP ( Simple Object Access Protocol )
- Format for sending messages over Internet between programs.
- XML-based
- Platform and language independent.
- Simple and extensible.
- Uses mainly HTTP as a Transport protocol: HTTP message contains a SOAP message as its payload section.
- Stateless, one-way: but applications can create more complex interaction patterns.

#### SOAP building blocks
- Envelope (required) identifies XML document as SOAP message.
- Header (optional) : contains header information.
- Body (required): call and response information.
- Fault (optional): errors that occured while processing message.

**![](https://lh7-us.googleusercontent.com/gZwqneLbb7kg0K9eG-ENWEwCCMcRVS6556ZzBj2KNvSvEYarh5OT8-HYe84UJ8NOa8TVKqig44RfvlE8P7JChWVCrIHV1qc3zk1Xtw-Oi7kHcz9W0YO5ldxScQbT8LKaCco5D7DWX7YAktJwi56yC18)**
- Request and response messages: Request invokes a method on a remote object. Response returns result of running the method.
- SOAP specification defines an "envelope" 
	- Envelope wraps the message itself. 
	- Message is a different vocabulary.
	- Namespace prefix is used to distinguish the two parts.

<hr>

Q3. **What are Web Services ?**

Ans.
- Web service is XML based phenomena. XML is data transformation language. It helps in interoperability and helps in applications talking to each other.
- Web services are those services which are available on with can be defined and accessible through a standardized URI (Uniform Resource Idendifier) and it works on message exchange type of protocol which is based on XML.

<hr>

Q4. **What is EDI ? What are it's advantages ?**

Ans. 
#### EDI ( Electronic Data Interchange )
- It is the computer to computer exchange of business data and documents between companies using standard formats recognized both nationally and internationally.
- Business data is all the information that is related to a company, such as sales data, customer contact information, and even website traffic statistics.
- For example of business data, when you visit a company's website, data is captured about what you looked at: what colors you preferred, how long you remained on a page and yes, even your physical location

#### EDI Advantages : 
- Reduced lead-time
- Reduction in number of errors
- Reduction in processing costs overall
- Availability of information at all times
- Planning becomes easier
- Long-term relationships between trading partners

<hr>

## PPT 14
Q1. **What is SLA ?**

Ans. 
#### Service Level Agreement ( SLA )
- Whenever a person wants to use cloud services there should be some kind of agreement
- This agreement should deal with the following things  :
	- Price of the service
	- Availability of the service
	- Qualitiy of the service
		- Performance
		- Security
		- Reliability
- It is a contract formed b/w the *Service Provider* and the *Service Consumer*.
- SLA contains certain *Service Level Objectives*
	- They might require more uptime.
	- They might require longer hours of availability.
	- They might require more security, performance, etc.

#### Short points for SLA : 
1. It is a set of services the provider guarantees to give the consumer
2. It defines a set of metrics that measure if the provider is offering the services as guaranteed.
3. An auditing mechanism to monitor the services.
4. The remedies available to the consumer and the provider if the terms are not satisfied.

For Example : 
- If a service provider says that they will keep an uptime of 95%, then there must be some agreement on that.

<hr>

Q2.**What are the types of SLA and what are the requirements of SLA?**

Ans.
#### Types of SLA
Present market place features two types of SLAs :
- *Off-the-shelf SLA* or *non-negotiable SLA* or *Direct SLA*
	- Non-conducive for mission-critical data or applications
	- Provider creates the SLA template and define all criteria viz. contract period, billing, response time, availability, etc.
	- Followed by the present day state-of-the-art clouds.
- *Negotiable SLA*
	- Negotiation via external agent
	- Negotiation via multiple external agents

#### Requirements of SLA ( SDPDHRTCMA )
1. *Security*
2. *Data Encryption*
3. *Privacy*
4. *Data Retention and Deletion*
5. *Hardware Erasure and Destruction*
6. *Regulatory Compliance*
7. *Transparency*
8. *Certification*
9. *Monitoring*
10. *Auditibility*

<hr>

## PPT 16

Q1. **What is a Relational Database Management System ?**

Ans. 
- Users/application programs interact with an RDBMS through SQL 
- RDBM parser:
	- Transforms queries into memory and disk-level operations
	- Optimizes execution time
- Disk-space management layer:
	-	Stores data records on pages of contiguous memory blocks
	- Pages are fetched from disk into memory as requested using pre fetching and page replacement policies.

<hr>

Q2. **What is the Database File System Layer ? Also mention different database storage techniques**

Ans.
Independent of OS file system.
Reason:
- To have a full control on retaining or releasing a page in memory.
- Files used by the DB may span multiple disks to handle large storage. 

Uses parallel I/0 systems, viz. RAID disk arrays or multiprocessor clusters.

#### Data Storage Methods
*Row-oriented storage*
- Optimal for write-oriented operations 
- Relational records: stored on contiguous disk pages
- Accessed through indexes (primary index) on specified columns. 
- $B^+$ - tree like storage.

*Column-oriented storage*
- Efficient for data-warehouse workloads that contain high-dimensional data. 
- Aggregation of measure columns need to be performed based on values from dimension columns.
- Projection of a table is stored as sorted by dimension values.
- Require multiple join-indexes: if different projections are to be indexed in sorted order.

<hr>

Q3. **What are the different Cloud File Systems ? Define GFS and HDFS**

Ans. 
*Google File System (GFS)*
- Designed to manage relatively large files using a very large distributed cluster of
commodity servers connected by a high-speed network
- Handles:
	- Failures even during reading or writing of individual files
	- Fault tolerant: a necessity
	- Support parallel reads, writes and appends by multiple simultaneous client programs

*Hadoop Distributed File System (HDFS)*
- Open source implementation of GFS architecture
-  Available on Amazon EC2 cloud platform

<hr>

## PPT 17
Q1. **What is MapReduce ? What are it's objectives**

Ans. 
 **MapReduce**
- It is a programming model developed at Google and associated implementation for processing and generating large data sets with a parallel, distributed algorithm on a cluster
- Objective:
	- Implement *large scale search*
	- *Text processing* on massively scalable web data that is stored using Bigtable and GFS distributed file system
- Designed for processing and generating large volumes of data via massively *parallel computations*, utilizing tens of thousands of processors at a time
- *Fault tolerant*: ensure progress of computation even if processors and networks fail

Example:
- Hadoop: open source implementation ot MapReduce (developed at Yahoo!)
- Available on pre-packaged AMis on Amazon EC2 cloud platform

<hr>

Q2. **What is Parallel Computing ? What are the types of parallel Database architectures ? Give a detailed Diagram**

Ans.
#### Models of Parallel Computing
It encompasses the nature and evolution of multiprocessor computer architecture 
1. **Shared Memory Model** : 
- Assumes that any process can access any memory location
2. **Distributed Memory Model** :
- Each processor can access only it's own memory and can communicate with other processors, using message passing.

#### Parallel Computing
> It was developed for computing intensive tasks

It was then applied to databases as well to create the following types of database architectures : 
1. **Shared Nothing** 
- It is a cluster of indpendent servers, each with their own disk space.
- Connected via a network
2. **Shared Disk**
- Hybrid Architecture
- Independent server clusters *share storage* through NAS ( Network attached Storage )
3. **Shared Memory**
- Suitable for servers with multiple CPU's
- Memory address space is shared

<hr>

Q3. **What is the MapReduce Model ? Explain the Mapping and Reducing phase of the process**

Ans.  

#### MapReduce Model

It is based on Parallel programming and is used by many applications that require large scale computing that involves thousands of processors.
- It uses a fault tolerant implementation and involves two phases : 
	- Map Operation
	- Reduce Operation
- A configurable number of 'mapper' processors and R 'Reducer' processors are assigned to work on a given problem

#### Map Phase : 
- Each mapper reads approximately $1/M$ of the input from the global file location
- $\text{Map} (k_1, v_1) -> [(k_2, v_2)]$
- It then writes the computation results in one file per reducer

#### Reduce Phase : 
- It finds the partial computations done by the mapper and then fetches those files.
- It groups up the result given by the mappers and writes the result back to the GFS system.

**![](https://lh7-us.googleusercontent.com/EV8Nhwao_w2h1eirhx9xYzZoXQYVNwkais1B6SgqVK9ddLCIU8OAHBAZR_cAPtl6ScsY_GuB2jJOwyFvZK94FADV-V851k1S-UKdl830IvUxqVIcwwwwwRY2GBohLQVtGRWHCKCVMw66xx6zHD1tLXs)**
<hr>

## PPT 18 

> This ppt contains 2 SLA based problems to be solved to check for violation of initial availability guarantee.
> Refer to the questions solved in the ESE last year paper, above.
> [Link to question](#availability-question)


## PPT 19
Q1. **What is resource management in Cloud Computing and what are it's objectives ? What are the types of resources available?**

Ans.

1. Cloud is an infinite resource pool that leverages resources for multiple users.
2. ( *from the users POV* ) It is a scalable service that works on a pay-as-you-go model 
3. ( *from providers POV* ) They have to maximize profit without compromising the quality of service or causing SLA violations.
4. ( *environment POV* )Reducing the carbon footprint and the amount of energy resources being used.

#### Resource Management : 
> It refers to the operations used to control how capabilities provided by cloud resources and services can be made available to others ( individuals or organizations alike ) in an efficient manner.

There are 2 types of resources in Hardware systems : 
- **Physical Resource** : 
	- Computer, disk, database, network, etc.
- **Logical Resource** : 
	- Execution, processors, monitoring, etc

The objectives of resource management are as follows : 
- Scalability
- Quality of service
- Optimal utilit
- Reduced overheads
- Improved throughput
- Reduced latency
- Specialized environment
- Cost effectiveness
- Simplified interface

<hr>

## PPT  20
Q1. **Explain the properties of Cloud Computing from an economic viewpoint**

Ans. 
#### Cloud Properties: Economic Viewpoint
- *Common Infrastructure*
	- pooled, standardized resources. with benefits generated bv statistical multiplexing.
- *Location-independence*
	- ubiquitous availability meeting performance requirements. with benefits deriving from latency reduction and user experience enhancement.
- *Online connectivity*
	- An enabler of other attributes ensuring service access. Costs and performance impacts Of network architectures can be quantified using traditional methods.
- *Utility pricing*
	- Usage-sensitive or pay-per-use pricing, with benefits applying in environments with variable demand levels. on-Demand Resources
	- Scalable, elastic resources provisioned and de-provisioned without delay or costs associated with change.

<hr>

> The questions are available here : [Link to questions on cost/hour](#cloud-and-in-house-server-comparision)
> [Link to MapReduce Questions](#mapreduce-based-questions)

<hr>

## PPT 21
Q1. **What are the various challenges and aspects  of resource management ?**

Ans. 
#### Resource Management — Challenges (Hardware)
- CPU (central processing unit)
- Storage
- Workstatbons
- Network elements

#### Resource Management — Challenges (Logical resources)
- Operating system
- Energy
- Network Throughput/ bandwidth
- Load balancing mechanisms
- Information security
- Delays
- APIs/(Applications Programming Interfaces)
- Protocols

#### Resource Management Aspects
- Resource provisioning
- Resource allocation
- Resource requirement mapping
- Resource adaptation
- Resource discovery
- Resource brokering
- Resource estimation
- Resource modeling

<hr>

## PPT 22

> Questions on green cloud computing have been completed before.
> [Link to Green Cloud Computing](#green-computing)

Q1. **What is the Green Cloud ?**

Ans.
#### Green Cloud
- Green cloud is an aspect of cloud computing that makes it more efficient
- Normally having multiple in house servers, networks, lan cables, etc,  entail huge power consumption.
- The cost of computing equipment, space, power etc is very high to purchase and to maintain.
- Green Cloud looks to reduce the carbon footprint by making more efficient use of such cloud resources.
- Running VM's ( Virtual Machines ) is one of the ways to compete this growing problem.
- Reducing CPU usage time, network usage time, etc, reduces the energy consumption in cloud infrastructure.

<hr>

Q2. **What is the impact of Cloud Data Centers on the environment ?**

Ans.

#### Impact of Cloud DC on Environment
- Data centers are not only expensive to maintain, but also unfriendly to the environment.
- Carbon emission due to Data Centers worldwide is now more than both
- Argentina and the Netherlands emission.
- High energy costs and huge carbon footprints are incurred due to the massive amount of electricity needed to power and cool the numerous servers hosted in these data centers.

<hr>

## PPT 23
Q1. **What is a sensor Cloud ? What are the different kinds of sensors and **
