# Cloud Service Models

## INFRASTRUCTURE AS A SERVICE, PLATFORM AS A SERVICE, AND SOFTWARE AS A SERVICE

### Infrastructure as a Service (IaaS)

Infrastructure as a service is what people typically envision when they think of
the cloud, as it provides access to the hardware needed to run applications. IaaS
essentially replicates a data center using on-prem legacy hardware in a cloud.
Companies who opt to run solely on an IaaS computing model choose to do the heavy
lifting of designing and maintaining their cloud service. This model requires
infrastructure engineers and architects who will be deeply involved in the development
and maintenance of the cloud.

Examples of IaaS services:

- Cisco
- Microsoft Azure
- Amazon Web Services (AWS)
- Google Compute Engine (GCE)
- Digital Ocean

Use IaaS:

- When you need control over your high-performing applications
- When you don’t have the finances to invest in hardware
- When you want to purchase only what you consume or need
- When you need to be able to change out specific hardware and software easily

Don’t Use IaaS:

- If you are not interested in or able to handle the management of a virtual machine
- If the vendor does not meet your security standards

### Platform as a Service (PaaS)

Platform as a service offers an additional layer of abstraction over IaaS, providing
necessary components beyond infrastructure. The platform layer typically includes
operating systems, pre-built development tools, testing, runtime, middleware, and
databases. By leveraging this model rather than managing the platform themselves,
developers can focus on functionality that adds business value.

Examples of PaaS services:

- Azure App Service
- Salesforce.com
- Google App Engine
- AWS Elastic Beanstalk
- OpenShift

Use PaaS:

- When developers are comfortable using standardized building blocks
- When developers require the specialized capabilities it provides but no internal
  team wants to own the service
- For services outside your core business area, such as automation, deployment and
  monitoring

Don’t Use PaaS:

- If your project needs proprietary building blocks
- When you are using low level or legacy languages for development
- If the application requires you to customize hardware and software
- When applications generate a transaction volume that might make PaaS services
  cost prohibitive

### Software as a Service (SaaS)

Software as a service delivers an entire software stack to users, who typically
just pay for the subscription. The SaaS model requires no application coding and
no hosting infrastructure.

The provider is 100% responsible for system updates, security, and any other
essential tasks. The SaaS model is basically outsourcing for your application or
workstream and is a wise choice when a full-featured, well-maintained product that
meets your business needs is already available.

Examples of SaaS services:

- Google apps (i.e., Gmail or Google Maps)
- Dropbox
- Salesforce
- YouTube
- Concur
- GoToMeeting
- MS Office 365

Use SaaS:

- For standard solutions requiring a low level of customization and internet access
  via multiple device types
- When you don't have the skills internally to install, run, and manage the software
- When it's more cost effective to let a specialist run the software
- When you're happy with the SaaS provider's data privacy, service and
  configuration/integration options

Don’t Use SaaS:

- When you need a high level of configuration, customization, or specialist integrations
- When you can run it yourself more effectively
- When you have compliance requirements that don’t permit outside hosting
- When extensive experience of business process customization is required

