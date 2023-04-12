Note: The files in this folder are mirrored from another location, do not edit directly.

# Supportability Review

Ensure business continuity with ongoing reviews and advice. Get faster resolutions, prevent incidents, minimize drift whilst staying conformant with our validated configurations.

## Notes
This script is intended to collect info from Rancher upstream cluster and RKE1 managed downstream clusters
- loremipsum ##add additional information
- loremipsum ##add additional information


### What's being collected?

Please review the below files for details:

- [cluster-collector.sh](./cluster-collector.sh)
- [nodes-collector.sh](./nodes-collector.sh)

## Pre-requisites

[] The tool has to run on node with the following requirements
  - Connectivity: 
      - Access to Rancher URL
                
      - Access to https://raw.githubusercontent.com/ to download the collect.sh script
      
      - Access to the repository ghcr.io/rancherlabs to download the image 
                
  - Packages:  
      - Docker 
       
      - wget or curl tool
   
[] Permissions: 
      - ⚠️ 🥦 💥 Generate Rancher bearer token. Truism, If the user that generates the token does not have permissions over the cluster, the script will fail. 
      [How to generate a token]((https://ranchermanager.docs.rancher.com/reference-guides/user-settings/api-keys#docusaurus_skipToContent_fallback)
      

## How to use

1. Download the `collect.sh` script on a Linux node and make it executable.

    Using wget
    ```shell
    wget https://raw.githubusercontent.com/rancherlabs/support-tools/master/collection/rancher/v2.x/supportability-review/collect.sh
    chmod +x collect.sh
    ```
   Using curl
   ```shell
    curl -OLs https://raw.githubusercontent.com/rancherlabs/support-tools/master/collection/rancher/v2.x/supportability-review/collect.sh
    chmod +x collect.sh
    ```
2. Set the required environment variables.
    ```shell
   export RANCHER_URL="https://rancher.example.com"
   export RANCHER_TOKEN="token-a1b2c:hp7nxfs25w5g7rlc6gkasddhzpphfjbgmcqg6g2kpv52gxg7tl2fgpq2q"
 
   ```
3. Run the collection script
The script needs to be run directly on the node, using the root user or a user in the docker group. Ensure the docker daemon is running.
```
 ./collect.sh
```
4. Share the generated support bundle with SUSE Rancher Support Team.
Output will be written  as a tar.gz archive in the same path where the script is run.

## Flags
Rancher Supportability Review
Usage: collect.sh [ --cluster --cluster]

All flags are optional.

[^1]
