
# Update Service

## Components List

- [Connector Channel](#connector-channel)
    * [Consumers](#Consumers)
        + [handle notification subscription](#handle-notification-subscription)
        + [handle async response](#handle-async-response)
        + [send_resource_to_device](#send-resource-to-device)        
- [Deployment Service](#deployment-service)
    * [Consumers](#Consumers)
        + [campaign manager](#campaign-manager)
        + [check manifest](#check-manifest)
        + [deleted manifest](#deleted-manifest)   
        + [device updated](#device-updated)
        + [log manifest sent devices](#log-manifest-sent-devices)
        + [update campaign_device_metadata](#update-campaign-device-metadata)
        + [update update campaign attributes](#update-update-campaign-attributes)
        + [account limit](#account-limit)        
- [Firmware Catalog](#firmware-catalog)
    * [Consumers](#Consumers)
        + [firmware account limit](#firmware-account-limit)
- [Campaign Engine](#campaign-engine)
    * [Consumers](#Consumers)
        + [start campaign Message](#start-campaign-message)
        + [stop campaign Message](#stop-campaign-message)
- [Campaign Device State](#campaign-device-state)
    * [Consumers](#Consumers)
        + [campaign device state](#campaign-device-state)
- [Campaign Device Resource Manager](#campaign-device-resource-manager)
    * [Consumers](#Consumers)
        + [device resource manager](#device-resource-manager)
- [Campaign Device Heartbeat](#campaign-device-heartbeat)
    * [Consumers](#Consumers)
        + [campaign device heartbeat](#campaign-device-heartbeat)
  


## **Connector Channel**
*Description*

### **Consumers**:

### *handle-notification-subscription*
 **Description:** Handle notification subscription change
 
 **Queue:** `connector-channel-handle-notification-subscription`
 _____
### *handle-async-response*
  **Description:** Handle async responses from mDS.
 Async ID may not have reached the cache by the time an async response is
 received - mDS sometimes returns the response to the request before returning the ID of the request to the
 originator(!) and so we can retry outside of the HTTP PUT request.
 
 **Queue:** `connector-channel-handle-async-response`
 _____
### *send-resource-to-device*
 **Description:** Send resource to a device
 
 **Queue:** `connector-channel-send-manifest`
 _____
## **Deployment Service**
*Description*

### **Consumers**:

### *campaign-manager*
 **Description:** Check campaigns for `state` and `when` fields, triggering an update event to start a campaign when ready.
 
 **Queue:** `deployment-service-campaign-manager-with-retry`
_____
### *check-manifest*
 **Description:** Check the manifest, splitting key tables if present and copying manifest_timestamp to update campaign.
 
 **Queue:** `deployment-service-check-manifest`
_____
### *deleted-manifest*
 **Description:** Handle firmware manifest deletions.
 
 **Queue:** `deployment-service-deleted-manifests`
_____
### *device-updated*
 **Description:** Consume messages sent when devices are updated.
    We look for certain fields changed in the Device Catalog record and update their equivalents
    in the corresponding CampaignDeviceMetadata record.
 
 **Queue:** `deployment-service-device-updated`
_____
### *log-manifest-sent-devices*
 **Description:** Relog devices that were-reached/could-not-be-reached for manifest upload.
 
 **Queue:** `deployment-service-log-manifest-sent-devices`
_____
### *update-campaign-device-metadata*
 **Description:** Consume device firmware updates from the connector channel and updates the Campaign Device Metadata."
 
 **Queue:** `deployment-service-update-deployment-device`
_____
### *update-update-campaign-attributes*
 **Description:** Update the cache of the update campaign state.
 
 **Queue:** `deployment-service-update-campaign-cache`
_____
### *account-limit*
 **Description:** Process account_limit message that sets the updatecampaign limit for the given account.
 
 **Queue:** `deployment-service-account-limits`
_____
## **Firmware Catalog**
*Description* 

### **Consumers**:

### *firmware-account-limit*
 **Description:** Process account_limit message that sets the firmware limits for the given account.
 
 **Queue:** `firmware-account-limits`
 _____
## **Campaign Engine**
### **Consumers**:

### *start-campaign-message*
 **Description:** Description
 
 **Queue:** `deployment-service-apply-firmware-update`
 _____
### *stop-campaign-message*
 **Description:** Description
 
 **Queue:** `deployment-service-campaign-engine-stop-campaign`
 _____
## **Campaign Device State**
### **Consumers**:

### *campaign-device-state*
 **Description:** Description
 
 **Queue:** `deployment-service-campaign-device-state`
_____
## **Campaign Device Resource Manager**
### **Consumers**:

### *device-resource-manager*
 **Description:** Description
 
 **Queue:** `update-service-device-resource-manager`
 _____
## **Campaign Device Heartbeat**
### **Consumers**:

### *campaign-device-heartbeat*
 **Description:** Description
 
 **Queue:** `deployment-service-campaign-device-heartbeat`
_____
