---
name: ASP.NET debugging enabled
severity: low
cvss-score: 5.3
cvss-vector: CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:N/A:N
cwe-id: CWE-489
cwe-name: Active Debug Code
compliance:
  owasp10: A5
  pci: 6.5.5

---            

The ASP.NET debug feature is useful for debugging ASP.NET web applications, and even be used for remote debugging. This feature can reveal sensitive information about the internals of the application, such as code snippets, environment variables, security keys, etc. All of this can be used by an attacker to increase the likelihood of an successful attack.

This debug feature should not be enabled in a production environment.


## How to fix

{% tabs aspnet-debugging-enabled %}
{% tab aspnet-debugging-enabled generic %}
ASP.NET debugging is a feature of the ASP.NET framework, configured in the `web.config` file. To disable it, you need to edit the `web.config` file and change the `debug` flag within your `compilation` directive to `false`:

```
    <configuration>  
        <system.web>  
            <compilation  
                debug="false"  
                ...  
            >  
            ...  
            </compilation>  
        </system.web>  
    </configuration>  

```
{% endtab %}

{% endtabs %}
