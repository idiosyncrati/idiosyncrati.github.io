## Live, Laugh, Sentinel


### Down to basics
To start off with Fortigate logs in KQL we can break down the first part of the query
```markdown
CommonSecurityLog
`//Vendor Parsing`
| where DeviceVendor == "Fortinet"  
`// Action - A large list of actions can occur but most common will be 'accept' or 'deny', traffic that has successfully passed through Fortigate policies can be filtered through != "deny"`
`// More information around Fortigate policies are defined here : [Fortigate Cookbook](https://docs.fortinet.com/document/fortigate/6.0.0/handbook/554066/firewall-policies).`
| where DeviceAction != "deny"    
```
