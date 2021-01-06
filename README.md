
# Update Service

## Table of contents

- [Connector Channel](#connector-channel)
    * [consumers](#consumers)
        + [handle notification subscription](#handle-notification-subscription)
        + [handle async response](#handle-async-response)
        + [send_resource_to_device](#send-resource-to-device)        
- [Deployment Service](#deployment-service)
    * [consumers](#consumers)
        + [campaign manager](#campaign-manager)
        + [check manifest](#check-manifest)
        + [deleted manifest](#deleted-manifest)   
        + [device updated](#device-updated)
        + [log manifest sent devices](#log-manifest-sent-devices)
        + [update campaign_device_metadata](#update-campaign-device-metadata)
        + [update update campaign attributes](#update-update-campaign-attributes)
        + [account limit](#account-limit)        
- [Firmware Catalog](#firmware-catalog)
    * [consumers](#consumers)
        + [firmware account limit](#firmware-account-limit)
- [Campaign Engine](#campaign-engine)
    * [consumers](#consumers)
        + [start campaign Message](#start-campaign-message)
        + [stop campaign Message](#stop-campaign-message)
- [Campaign Device State](#campaign-device-state)
    * [consumers](#consumers)
        + [campaign device state](#campaign-device-state)
- [Campaign Device Resource Manager](#campaign-device-resource-manager)
    * [consumers](#consumers)
        + [device resource manager](#device-resource-manager)
- [Campaign Device Heartbeat](#campaign-device-heartbeat)
    * [consumers](#consumers)
        + [campaign device heartbeat](#campaign-device-heartbeat)
  


## Connector Channel
*Description*

### consumers:
#### handle-notification-subscription
 text
#### handle-async-response
text
#### send-resource-to-device
text

## Deployment Service
*Description*
### consumers:
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
### consumers:
#### firmware-account-limit
 text
 
## Campaign Engine
### consumers:
#### campaign-manager
Description

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
