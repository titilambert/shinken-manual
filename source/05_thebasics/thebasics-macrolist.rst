.. _thebasics-macrolist:




============================
 Standard Macros in Shinken 
============================


Standard macros that are available in Shinken are listed here. On-demand macros and macros for custom variables are described :ref:`here <thebasics-macros>`.



Macro Validity 
===============


Although macros can be used in all commands you define, not all macros may be “valid” in a particular type of command. For example, some macros may only be valid during service notification commands, whereas other may only be valid during host check commands. There are ten types of commands that Nagios recognizes and treats differently. They are as follows:

  - Service checks
  - Service notifications
  - Host checks
  - Host notifications
  - Service :ref:`event handlers <advancedtopics-eventhandlers>` and/or a global service event handler
  - Host :ref:`event handlers <advancedtopics-eventhandlers>` and/or a global host event handler
  - :ref:`OCSP <configuringshinken-configmain#configuringshinken-configmain-ocsp_command>` command
  - :ref:`OCHP <configuringshinken-configmain#configuringshinken-configmain-ochp_command>` command
  - Service :ref:`performance data <advancedtopics-perfdata>` commands
  - Host :ref:`performance data <advancedtopics-perfdata>` commands

The tables below list all macros currently available in Shinken, along with a brief description of each and the types of commands in which they are valid. If a macro is used in a command in which it is invalid, it is replaced with an empty string. It should be noted that macros consist of all uppercase characters and are enclosed in $ characters.



Macro Availability Chart 
=========================


Legend:


^ Macro Name ^ Service Checks ^ Service Notifications ^ Host Checks ^ Host Notifications ^ Service Event Handlers and :ref:`OCSP <configuringshinken-configmain#configuringshinken-configmain-ocsp_command>` ^ Host Event Handlers and :ref:`OCHP <configuringshinken-configmain#configuringshinken-configmain-ochp_command>` ^ Service Perf Data ^ Host Perf Data ^



Macro Descriptions 
===================





Notes 
======


-1 These macros are not valid for the host they are associated with when that host is being checked (i.e. they make no sense, as they haven't been determined yet).

-2 These macros are not valid for the service they are associated with when that service is being checked (i.e. they make no sense, as they haven't been determined yet).

-3 When host macros are used in service-related commands (i.e. service notifications, event handlers, etc) they refer to the host that the service is associated with.

-4 When host and service summary macros are used in notification commands, the totals are filtered to reflect only those hosts and services for which the contact is authorized (i.e. hosts and services they are configured to receive notifications for).

-5 These macros are normally associated with the first/primary hostgroup associated with the current host. They could therefore be considered host macros in many cases. However, these macros are not available as on-demand host macros. Instead, they can be used as on-demand hostgroup macros when you pass the name of a hostgroup to the macro. For example: $HOSTGROUPMEMBERS:hg1$ would return a comma-delimited list of all (host) members of the hostgroup hg1.

-6 These macros are normally associated with the first/primary servicegroup associated with the current service. They could therefore be considered service macros in many cases. However, these macros are not available as on-demand service macros. Instead, they can be used as on-demand servicegroup macros when you pass the name of a servicegroup to the macro. For example: $SERVICEGROUPMEMBERS:sg1$ would return a comma-delimited list of all (service) members of the servicegroup sg1.

-7 These macros are normally associated with the first/primary contactgroup associated with the current contact. They could therefore be considered contact macros in many cases. However, these macros are not available as on-demand contact macros. Instead, they can be used as on-demand contactgroup macros when you pass the name of a contactgroup to the macro. For example: $CONTACTGROUPMEMBERS:cg1$ would return a comma-delimited list of all (contact) members of the contactgroup cg1.

-8 These acknowledgement macros are deprecated. Use the more generic $NOTIFICATIONAUTHOR$, $NOTIFICATIONAUTHORNAME$, $NOTIFICATIONAUTHORALIAS$ or $NOTIFICATIONAUTHORCOMMENT$ macros instead.

-9 These macro are only available as on-demand macros - e.g. you must supply an additional argument with them in order to use them. These macros are not available as environment variables.

-10 Summary macros are not available as environment variables if the :ref:`use_large_installation_tweaks <configuringshinken-configmain#configuringshinken-configmain-use_large_installation_tweaks>` option is enabled, as they are quite CPU-intensive to calculate.

