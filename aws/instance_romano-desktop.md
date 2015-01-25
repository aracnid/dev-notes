- **AMI**: CentOS 7 (x86_64) with Updates HVM

- **Instance Type**: m3.large
  - vCPUs: 2
  - Memory: 7.5 GiB
  - Instance Storage: 1 x 32 GB (SSD)
  
- **Configuration**:
  - Availability Zone: us-east-1c (This must match the zone of the additional data volume to attach.)
  
- **Storage**:
  - Type: root
  - Device: /dev/sda1
  - Size: 8 GiB
  - Volume Type: General Purpose (SSD)
  
- **Tags**:
  - Name: romano-desktop
  
- **Security Group**:
  - Name: romano-desktop-group
    - TCP: Port 22 from Anywhere (SSH)
    - TCP: Port 4000 from Anywhere (NX)
    - UDP: Port 4369 from Anywhere (NX)
    
- **Key Pair**:
  - Name: romano-desktop-keys
