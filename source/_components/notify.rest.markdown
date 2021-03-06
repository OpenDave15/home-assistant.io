---
layout: page
title: "REST"
description: "Instructions how to add RESTful notifications to Home Assistant."
date: 2016-02-12 07:00
sidebar: true
comments: false
sharing: true
footer: true
ha_category: Notifications
---


The `rest` notification platform allows you to deliver [RESTful](https://en.wikipedia.org/wiki/Representational_state_transfer) notifications from Home Assistant to another party.

To enable the REST notification in your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
notify:
  name: NOTIFIER_NAME
  platform: rest
  resource: http://IP_ADDRESS/ENDPOINT
  method: GET
  message_param_name: MESSAGE_PARAMETER_NAME
  title_param_name: TITLE_PARAMETER_NAME
  target_param_name: TARGET_PARAMETER_NAME
```

Configuration variables:

- **name** (*Optional*): Setting the optional parameter `name` allows multiple notifiers to be created. The default value is `notify`. The notifier will bind to the service `notify.NOTIFIER_NAME`.
- **resource** (*Required*): The resource or endpoint that will recieve the value.
- **method** (*Optional*): The method of the request. Default is GET.
- **message_param_name** (*Optional*): Parameter name for the message. Defaults to `message`.
- **title_param_name** (*Optional*): Parameter name for the title. Defaults to none.
- **target_param_name** (*Optional*): Parameter name for the target. Defaults to none.

To use notifications, please see the [getting started with automation page](/getting-started/automation/).

