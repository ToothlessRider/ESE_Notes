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
$\int_{\frac{\pi}{2}}^{\pi} R(t) \, dt = \int_{\frac{\pi}{2}}^{\pi} 45(\sin(t) + \frac{\pi}{9}\cos(t)) \, dt$
$= 45 \int_{\frac{\pi}{2}}^{\pi} \sin(t) \, dt + 45 \cdot \frac{\pi}{9} \int_{\frac{\pi}{2}}^{\pi} \cos(t) \, dt$
$= 45 \left[ -\cos(t) \right]_{\frac{\pi}{2}}^{\pi} + 45 \cdot \frac{\pi}{9} \left[ \sin(t) \right]_{\frac{\pi}{2}}^{\pi}$
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

**Calculate the Cost:**

The cost to provision one unit of cloud resource for one unit time is 0.9 units.
$\text{Penalty Cost} = 0.9 \times \left( 70 - \frac{20\pi}{9} \right)$
$= 0.9 \times 70 - 0.9 \times \frac{20\pi}{9}$
$= 63 - 2\pi$

So, the penalty cost for the delayed provisioning is:
$63 - 2\pi \approx 63 - 6.28 = 56.72 \text{ units}$

Thus, the penalty cost is approximately **56.72 units**.



