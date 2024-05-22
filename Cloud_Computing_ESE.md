#  Cloud_Computing_ESE
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/ESE_Notes.git)

Q1. a. **Differentiate between web service SLA and Cloud SLA. (At least 4 points).**

Ans. 
| **Criteria**               | **Web Service SLA**                                     | **Cloud SLA**                                              |
|----------------------------|---------------------------------------------------------|------------------------------------------------------------|
| **Scope of Services**      | Specific web service (API, web app)  [ SaaS and PaaS]                    | Broad range of cloud services (compute, storage, etc.) [IaaS]   |
| **Performance Metrics**    | API response time, error rates, transaction throughput  | VM uptime, storage I/O, database availability, network latency |
| **Responsibility and Control** | Full control by service provider                      | Shared responsibility between provider and customer        |
| **Outage and Compensation**| Credits/refunds for specific service downtime           | Complex service credits for various cloud services         |

<hr>

Q1. b. **What is the need of Universal Description Discover and Integration
(UDDI)? Demonstrate UDDI in detail.**

Ans. 

### Need for Universal Description, Discovery, and Integration (UDDI)

UDDI is essential for:

1. **Discovery**: Allows businesses to find web services offered by other companies.
2. **Integration**: Simplifies service integration by standardizing service descriptions.
3. **Interoperability**: Ensures compatibility across different platforms and languages.
4. **Publication**: Enables businesses to publish their services for discovery and use by others.

### Key Components and Operations of UDDI

#### Components

1. **BusinessEntity**: Describes the business offering web services.
2. **BusinessService**: Details the services provided by the business.
3. **BindingTemplate**: Specifies technical details, including access points.
4. **tModel**: Represents a technical specification the service adheres to.

#### Operations

1. **Publishing Services**: Businesses publish their services using the `publish` API.
2. **Finding Services**: Users search for services using the `inquiry` API.
3. **Retrieving Details**: Detailed service information is retrieved for integration.

### Example Workflow

1. **Publishing a Service**:
   - A company, "HealthCorp," publishes a web service.
   - HealthCorp creates a `BusinessEntity` entry with its details.
   - Within this entity, HealthCorp creates a `BusinessService` entry for their "PatientRecordsService."
   - A `BindingTemplate` specifies the URL and technical details.
   - A `tModel` is created or referenced if the service adheres to a specific standard.

2. **Finding a Service**:
   - A user, "ClinicAppDev," searches for a patient records service.
   - ClinicAppDev queries the UDDI registry for services named "PatientRecordsService" or a specific tModel.
   - UDDI returns matching services.
   - ClinicAppDev retrieves details about "HealthCorp's PatientRecordsService," including access URLs and technical specifics.

3. **Integrating with the Service**:
   - ClinicAppDev uses the retrieved information to integrate HealthCorp's service into their application.
   - They utilize the provided technical details to interact with the service.

### UDDI Example in XML

**1. BusinessEntity XML:**
```xml
<businessEntity businessKey="uuid:abcd1234-abcd-1234-abcd-1234567890ab">
    <name>HealthCorp</name>
    <description>Provider of healthcare solutions</description>
    <contacts>
        <contact>
            <personName>Jane Smith</personName>
            <email>jane.smith@healthcorp.com</email>
        </contact>
    </contacts>
</businessEntity>
```

**2. BusinessService XML:**
```xml
<businessService serviceKey="uuid:bcde2345-bcde-2345-bcde-234567890bcd" businessKey="uuid:abcd1234-abcd-1234-abcd-1234567890ab">
    <name>PatientRecordsService</name>
    <description>Provides patient records data</description>
    <bindingTemplates>
        <bindingTemplate bindingKey="uuid:cdef3456-cdef-3456-cdef-34567890cdef">
            <accessPoint>http://api.healthcorp.com/patientrecords</accessPoint>
        </bindingTemplate>
    </bindingTemplates>
    <categoryBag>
        <keyedReference tModelKey="uuid:defg4567-defg-4567-defg-4567890defgh" keyName="Standard" keyValue="REST"/>
    </categoryBag>
</businessService>
```

**3. tModel XML:**
```xml
<tModel tModelKey="uuid:defg4567-defg-4567-defg-4567890defgh">
    <name>PatientRecordsService REST API</name>
    <description>Technical model for HealthCorp's PatientRecordsService</description>
    <overviewDoc>
        <overviewURL>http://api.healthcorp.com/patientrecords/spec</overviewURL>
    </overviewDoc>
</tModel>
```

### Conclusion

UDDI provides a standardized way for businesses to publish, discover, and integrate web services, ensuring interoperability and simplifying the integration process across diverse systems.

<hr>

Q1. c. **Consider the peak computing demand for an organization is 200 units. The demand as a function of time can be expressed as:
$D(t) = 25\sin(t)$ 0 <= t <π/2 
$D(t) = 45\sin(t)$ π/2 <= 1 <π 
The resource provisioned by the cloud to satisfy the current demand at time t is given as:
$R(t) = D(t) + \delta \frac{d(D(t))}{dt}$
Where, δ is the delay in provisioning the extra computing resource on demand. The cost to provision unit cloud resource for unit time is 0.9 units. Calculate the penalty. (Assume the delay in provisioning is π/9 time units and the minimum demand is 0.)**

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

Now, we need to calculate the cost of provisioning the extra resource. The penalty is the cost of provisioning the resources due to the delay. We need to integrate $R(t)$ over the given time periods and then calculate the cost.

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
$\text{Penalty Cost} ∝ \int_0^{t}R(t) - D(t)$

$∝ |70 - (70 - \frac{20\pi}{9})|$

$∝ | \frac{20\pi}{9}|$

$Penalty ∝ 6.9813$

<hr>

Q1. d. **Suppose a cloud guarantees a service availability for 99% of time.
Let a third party application runs in the cloud for I0 hours/day. At
the end of one month, it was found that total outage is 9.25 hours.
Find out whether the provider has violated the initial availability
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

Q2. a. **Consider the peak computing demand for an organization is 500 units. The demand as a function of time can be expressed as $D(t)=80(1+e^{-t})$ Baseline (owned) unit cost is 320 and cloud unit cost is 400. In this situation is cloud cheaper than owning for a period of 500 time units?**

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

=$32000 \times (501−e^{−500})$

≈$32000 \times(501−0)≈80×(501−0)$ (since $e^{−500}$ is extremely close to 0)

=$32000 \times {501}$

=$₹1,60,32,000$

### Compare Costs:
Utility ( U ) = $\frac{C_t}{B_t}$

= $\frac{₹1,60,32,000}{₹8,00,00,000}$
= $0.2004$

Since the Cost of cloud is almost $\frac{1}{5}$ times lesser than the in-house, it is cheaper

<hr>

Q2. b. **What is map-reduce? Appy to the following word-count problem with the input: 
Fl: The store opens in the morning. 
F2: The store opens at 9am.**

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

Q2. c. **Discuss Google File System (GFS). In a map reduce framework consider the HDFS block size is 256MB. We have 3 files of size 128KB, 258MB, and 260MB. How many blocks will be created by Hadoop framework?**

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

Q2. d. **Apply map reduce to the following word-count problem, with the
input:
Fl: Cheer, Fear, Rear
F2: Cycle, Cycle, Rear
F3: Cheer, cycle, Fear**

Ans. 
To solve the word-count problem using MapReduce with the given input files, we can follow these steps:

1. **Map Phase**:
   - Read each input file.
   - Tokenize each line into words.
   - For each word, emit a key-value pair where the word is the key and the value is 1.

2. **Shuffle and Sort Phase**:
   - Shuffle the key-value pairs so that all pairs with the same key are grouped together.
   - Sort the grouped pairs by key.

3. **Reduce Phase**:
   - For each unique word, sum up the values (counts) associated with that word.
   - Emit a key-value pair where the word is the key and the sum of counts is the value.

Let's apply these steps to the given input:

### Map Phase:
For each input file, we tokenize the lines into words and emit key-value pairs:

For Fl:
- (Cheer, 1), (Fear, 1), (Rear, 1)

For F2:
- (Cycle, 1), (Cycle, 1), (Rear, 1)

For F3:
- (Cheer, 1), (cycle, 1), (Fear, 1)

### Shuffle and Sort Phase:
After shuffling and sorting by key:

(Cheer, [1, 1])
(Cycle, [1, 1])
(Fear, [1, 1])
(Rear, [1])

### Reduce Phase:
For each unique word, sum up the counts:

- Cheer: 1 + 1 = 2
- Cycle: 1 + 1 = 2
- Fear: 1 + 1 = 2
- Rear: 1

### Output:
The final output will be the word counts:

- Cheer: 2
- Cycle: 2
- Fear: 2
- Rear: 1

This demonstrates how MapReduce can efficiently solve the word-count problem by distributing the workload across multiple nodes in a parallel and fault-tolerant manner.

{'Cheer,': 2, 'Fear,': 1, 'Rear': 2, 'Cycle,': 3, 'Fear': 1}

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
calculating the average of a set of integers in MapReduce. Suppose A= (15, 25, 35, 45, 55, 65, 75) is a set of integers. Take 4 mapper nodes and 1 reducer node. Show the map and reduce outputs.**

Ans.
$A = (15, 25, 35, 45, 55, 65, 75 )$

Mapper Nodes = 4 
| Mapper | Numbers | Avg | Count |
|--|--|--|--|
|$M_1$| 15, 25 | 20 | 2 |
|$M_2$| 35, 45 | 40 | 2 |
|$M_3$| 55, 65 | 60 | 2 |
|$M_4$| 75 | 75 | 1 |

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
- Shared memory
	- Suitable for servers with multiple CPUs.
	- Memory address space is shared and managed by a symmetric multi-processing (SMP) operating system.
	- SMP schedules processes in parallel exploiting all the
processors.
- Shared Nothing
	- Cluster of independent servers each with its own disk space.
	- Connected by a network.
- Shared Disk
	- Hybrid Architecture
	- Independent server clusters share storage through high speed network storage viz. Network attached storage (NAS) or SAN (Storage Area Network).
	- Clusters are connected to the storage via: standard ethernet or
faster fiber channel or Infiniband connections.

**![](https://lh7-us.googleusercontent.com/9aUAjBrPrEeCT9lK74R8n1AVmPS4jmlE3Mp07b_dgWsQt_tf3dr9d8aTZLVD9TkFlz2Y0it7p4wxJJyk49XFHY0GvX33Wjb7G7kudL5MMRnQYv_NeP58nnBZcjjVSHuWhrzvrk68VoW3hBRJmvkX_5M)**
<hr>

Q4. b **Describe Openstack Cloud Architecture and its key components.**

Ans.
OpenStack is a cloud operating system that controls large pools of compute,
storage, and networking resources throughout a datacenter, all managed
through a dashboard that gives administrators control while empowering their
users to provision resources through a web interface.

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
<hr>

Q4. c. **Write pseudo codes for computing total and calculate average salary of on organization ABC while grouping them by Gender (male or female) using MapReduce. The input is as follows:
Name, Gender. Salary
Sam, M, 10000
Shalini, F. 15000**

Ans. 

<hr>

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

Q5. a. **A company Y needs to support a spike in demand when it becomes
popular followed potentially by a reduction once some of the
visitors turn away. The company has two options to satisfy the requitements which are given in the following table :**
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

<hr>

Q5. b. **Consider a scenario where a company Y wants to use a cloud service from a provider P. The service level agreement (SLA) guarantees negotiated between the two parties prior to initiating the business are as follows:
Avaialbility guarantee 99.95% time over the service period.
Service period: 31 days
Max service hours per day: 8 hours
Cost: Rs. 70/- per day
Service credits are awarded to customers if availability guarantees are not satisfied. Monthly connectivity uptime service level are given as:**
|Monthly uptime connectivity (%)| Service credit|
|--|--|
|<99.95%|20%|
|<99%|25%|
**However, in reality it was found that over the service period, the cloud service suffered 7 outages of the duration: 5 hrs, 20min, 2 hr 20 min, 20min, 3hrs 25 min. 35min, 2 hr, each on different days, due to which normal service guarantees were violated. If SLA negotiation are honoured, compute the effective cost payable towards buying the cloud service.**

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

<br> 

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


<hr>

## PPT - 16

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


