
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
  


## **Connector Channel**
*Description*

### **consumers**:

### *handle-notification-subscription*
 **Description:** Handle notification subscription change
 
 **Queue:** `connector-channel-handle-notification-subscription`
 
### *handle-async-response*
  **Description:** Handle async responses from mDS.
 Async ID may not have reached the cache by the time an async response is
 received - mDS sometimes returns the response to the request before returning the ID of the request to the
 originator(!) and so we can retry outside of the HTTP PUT request.
 
 **Queue:** `connector-channel-handle-async-response`
 Routing key: 

### *send-resource-to-device*
 **Description:** Send resource to a device
 
 **Queue:** `connector-channel-send-manifest`

## **Deployment Service**
*Description*

### **consumers**:

### *campaign-manager*
 **Description:** Check campaigns for `state` and `when` fields, triggering an update event to start a campaign when ready.
 
 **Queue:** `deployment-service-campaign-manager-with-retry`

### *check-manifest*
 **Description:** Check the manifest, splitting key tables if present and copying manifest_timestamp to update campaign.
 
 **Queue:** `deployment-service-check-manifest`

### *deleted-manifest*
 **Description:** Handle firmware manifest deletions.
 
 **Queue:** `deployment-service-deleted-manifests`

### *device-updated*
 **Description:** Consume messages sent when devices are updated.
    We look for certain fields changed in the Device Catalog record and update their equivalents
    in the corresponding CampaignDeviceMetadata record.
 
 **Queue:** `deployment-service-device-updated`

### *log-manifest-sent-devices*
 **Description:** Relog devices that were-reached/could-not-be-reached for manifest upload.
 
 **Queue:** `deployment-service-log-manifest-sent-devices`

### *update-campaign-device-metadata*
 **Description:** Consume device firmware updates from the connector channel and updates the Campaign Device Metadata."
 
 **Queue:** `deployment-service-update-deployment-device`

### *update-update-campaign-attributes*
 **Description:** Update the cache of the update campaign state.
 
 **Queue:** `deployment-service-update-campaign-cache`

### *account-limit*
 **Description:** Process account_limit message that sets the updatecampaign limit for the given account.
 
 **Queue:** `deployment-service-account-limits`

## **Firmware Catalog**
*Description*

### **consumers**:

### *firmware-account-limit*
 **Description:**
 
 **Queue:** 
 
## **Campaign Engine**
### **consumers**:

### *start-campaign-message*
 **Description:**
 
 **Queue:** 
 
### *stop-campaign-message*
 **Description:**
 
 **Queue:** 
 
## **Campaign Device State**
### **consumers**:

### *campaign-device-state*
 **Description:**
 
 **Queue:** 

## **Campaign Device Resource Manager**
### **consumers**:

### *device-resource-manager*
 **Description:**
 
 **Queue:** 
 
## **Campaign Device Heartbeat**
### **consumers**:

### *campaign-device-heartbeat*
 **Description:**
 
 **Queue:** 
