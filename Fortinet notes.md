FortiAnalyzer aggregates log data from one or more Fortinet devices, thereby acting as a centralized log repository. Log aggregation provides a single channel for accessing your complete network data, so you don’t need to access multiple devices, several times a day.
![[Pasted image 20241012030316.png]]
	Reports
	Events 
	Archive 
- - -
#### FA supports SQL specifically PostgreSQL DB
#### FA has 2 modes Analyzer and collector
- Analyzer(Forwardable to syslog/SEF):
When operating in analyzer mode, the device acts as a central log aggregator for one or more log collectors, such as a FortiAnalyzer device operating in collector mode, or any other supported device sending logs. Analyzer is the default operating mode.
![[Pasted image 20241012031536.png]]


- Collector(real time forwarding only and Archiving not analyzing):
When operating in collector mode, the device collects logs from multiple devices and then forwards those logs, in their original binary format, to another device, such as a FortiAnalyzer operating in analyzer mode. It can also send them to a syslog server or a common event format (CEF) server, depending on the forwarding mode. A collector does not have the same feature-rich options as an analyzer, because its only purpose is to collect and forward logs. It does not allow event management or reporting.
![[Pasted image 20241012031818.png]]

- Security fabric:
Correlate UTM logs for bandwidth threats and also it know the MAC addresses for FortiGate devices therefore no repetitive logs except natting logs 
no need for configuration each device will still logs to FA event if root FortiGate device is down.

How Security fabric get rid of duplicated logs:
![[Pasted image 20241012032930.png]]
FA supports operation modes:
member(HA) -> Doesn't forward to Supervisor. Supervisor is using API only / has some FA features still 
supervisor (Without HA) -> root. one per fabric SOC can view members and their ADOM's. Incidents and events are logged to it using API
![[Pasted image 20241012033705.png]]
Same time zone for all 
- - -
ADOMs
- It group devices based on their geographical locations b that it divides the administrations
- Manage data policies and space for each ADOM
![[Pasted image 20241012034146.png]]
Not enabled by default 
- - -
Tools(Locally and remotely):
CLI mode PuTTY SSH, Telnet 
GUI:
	Collector: no Fortiview or incident or Reports / SQL database is disabled by default and Can be enabled from CLI
	Analyzer: all
all changes made will reflect immediately without restart
- - -
## Logging
Troubleshooting / IR / NW load
Creating NW baselines / getting used to traffic bursts and usual ports
Balance between log storage and security risk with adherence to regulations by protorizing the src and dst also the frequancy and time and events

###### Log Types:
![[Pasted image 20241012040225.png]]














