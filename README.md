
# Update Service

## Table of contents

- [Connector Channel](#connector-channel)
    * [workers](#workers)
        + [handle notification subscription](#handle-notification-subscription)
        + [handle async response](#handle-async-response)
        + [send_resource_to_device](#send-resource-to-device)        
- [Deployment Service](#deployment-service)
    * [workers](#workers)
        + [campaign manager](#campaign-manager)
        + [check manifest](#check-manifest)
        + [deleted manifest](#deleted-manifest)   
        + [device updated](#device-updated)
        + [log manifest sent devices](#log-manifest-sent-devices)
        + [update campaign_device_metadata](#update-campaign-device-metadata)
        + [update update campaign attributes](#update-update-campaign-attributes)
        + [account limit](#account-limit)        
- [Firmware Catalog](#firmware-catalog)
    * [workers](#workers)
        + [firmware account limit](#firmware-account-limit)
- [Campaign Engine](#campaign-engine)
- [Campaign Device State](#campaign-device-state)
- [Campaign Device Resource Manager](#campaign-device-resource-manager)
- [Campaign Device Heartbeat](#campaign-device-heartbeat)


## Connector Channel
*Description*

### workers:
#### handle-notification-subscription
 text
#### handle-async-response
text
#### send-resource-to-device
text

## Deployment Service
*Description*
### workers:
#### campaign-manager
Description
#### check-manifest
Description
#### deleted-manifest
Description
#### device-updated
Description
#### log-manifest-sent-devices
Description
#### update-campaign-device-metadata
Description
#### update-update-campaign-attributes
Description
#### account-limit

## Firmware Catalog
*Description*
### workers:
#### firmware-account-limit
 text
 
## Campaign Engine
```text
consumers:
    ├── handle_notification_subscription
    ├── handle_async_response
    └── send_resource_to_device
```

## Campaign Device State
```text
consumers:
    ├── handle_notification_subscription
    ├── handle_async_response
    └── send_resource_to_device
```

## Campaign Device Resource Manager
```text
consumers:
    ├── handle_notification_subscription
    ├── handle_async_response
    └── send_resource_to_device
```

## Campaign Device Heartbeat
```text
consumers:
    ├── handle_notification_subscription
    ├── handle_async_response
    └── send_resource_to_device
```
