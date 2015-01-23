- **AMI**: CentOS 7 (x86_64) with Updates HVM

- **Instance Type**: m3.large
  - vCPUs: 2
  - Memory: 7.5 GiB
  - Instance Storage: 1 x 32 GB (SSD)
  
- ** Configuration**:
  default
  
- **Storage**:
  - Type: root
  - Device: /dev/sda1
  - Size: 10 GiB
  - Volume Type: General Purpose (SSD)
  
- **Tags**:
  - Name: romano-desktop
  
- **Security Group**:
  - Name: romano-desktop-group
    - SSH: (TCP) Port 22 from Anywhere
    
- **Key Pair**:
  - Name: romano-desktop-keys
