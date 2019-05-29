# 28/may/2019
Many thanks to [schubergphilis](https://github.com/schubergphilis/sensu-plugins-prometheus-checks)

# 29/may/2019
Allow environmental variables to be configured in configuration

```	

	config: 
	  sensu_socket:
	    address: "127.0.0.1"
	    port: 3030
	  prometheus:
	    endpoint: "localhost:9090"
	    	    
```

Allow reversed warning/critical levels

```

    cfg:
      type: 'reverse'
      warn: 20
      crit: 15		# Note: critical < warning < expected
      
```

Add custom data to events

```

    definition:
      handle: false                                             # Boolean
      handlers: []                                              # Array      
      source: "prefix_TEMPLATE_lbl_TEMPLATE_postfix"            # Templated String: Replace 'lbl' by Prometheus label named 'lbl'
      custom_data:													# Hash (recursive lookup)
        runbook: 'TEMPLATE_instance_TEMPLATE'						# Templated String

```

Alternative source through fixed Prometheus label

```

	source_label: 'role'		# When not using definition (source template), use simple label (Defaults to 'app' and 'instance')
	

```
