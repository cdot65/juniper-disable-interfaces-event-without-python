# Look Ma, No Scripts

This configuration example will allow you to trigger configuration changes when an event takes place, without any scripting

```junos
event-options {
    policy SHUTDOWN_IFACE {
        events rpd_ospf_nbrdown;
        then {
            change-configuration {
                commands {
                    "set interfaces ge-0/0/0 disable";
                    "set interfaces ge-0/0/1 disable";
                }
            }
        }
    }
}
```
