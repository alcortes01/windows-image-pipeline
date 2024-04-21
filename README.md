# Windows Image Pipeline
Pipeline to create Windows images with each process involved.

```mermaid
sequenceDiagram
    participant Image_Creator as "Image Creator"
    participant Windows_ISO as "Windows ISO"
    participant Organization_Tools as "Organization Tools"
    participant Software_Repository as "Software Repository"
    participant Security_Hardening as "Security Hardening"
    participant Image_Repository as "Image Repository"
    participant VDI_Teams as "VDI Teams (Citrix, VMWare, ESXi)"
    participant CI_CD_Tool as "CI/CD Tool"

    Image_Creator->>CI_CD_Tool: Trigger CI/CD Pipeline
    CI_CD_Tool->>Windows_ISO: Download Latest Windows ISO
    CI_CD_Tool->>Organization_Tools: Download Organization Tools
    CI_CD_Tool->>Software_Repository: Download Required Software

    CI_CD_Tool->>CI_CD_Tool: Create New Windows Image
    CI_CD_Tool->>CI_CD_Tool: Install Windows
    CI_CD_Tool->>CI_CD_Tool: Install Organization Tools
    CI_CD_Tool->>CI_CD_Tool: Install Required Software

    CI_CD_Tool->>Security_Hardening: Apply Security Hardening
    Security_Hardening->>CI_CD_Tool: Return Hardened Image

    CI_CD_Tool->>CI_CD_Tool: Build and Test Image
    CI_CD_Tool->>Image_Repository: Upload Image to Repository

    Image_Repository->>VDI_Teams: Provide Image for VDI Deployment

    VDI_Teams->>VDI_Teams: Deploy Workstations and Servers
    VDI_Teams->>Final_Users: Provide Workstations and Servers to Final Users
```

## Participants
#### Image Creator
The person or team responsible for triggering the CI/CD pipeline to create a new Windows image.

#### Windows ISO
The source of the Windows operating system installation media.

#### Organization Tools
The repository of organization-specific tools and software.

#### Software Repository
The repository of required software applications.

#### Security Hardening
The process of applying security configurations and patches to the image.

#### Image Repository
The storage location for the final Windows image.

#### VDI Teams
The teams responsible for deploying the Windows image to virtual desktop infrastructure (VDI) environments.

#### CI/CD Tool
The tool responsible for managing the entire process, from downloading components to deploying the final image.

## Process
The process involves creating a new Windows image, installing organization tools and software, applying security hardening, building and testing the image, and deploying it to the image repository for VDI teams to use.

## Processes with explanations
### 1. Trigger CI/CD Pipeline
#### The Image Creator triggers the CI/CD pipeline to start the process of creating a new Windows image.

### 2. Download Windows ISO
#### The CI/CD tool downloads the latest Windows ISO from the Windows ISO participant.

### 3. Download Organization Tools
#### The CI/CD tool downloads the necessary organization tools from the Organization Tools participant.

### 4. Download Required Software
#### The CI/CD tool downloads the required software applications from the Software Repository participant.

### 5. Create New Windows Image
#### The CI/CD tool creates a new Windows image using the downloaded components.

### 6. Install Windows
#### The CI/CD tool installs the Windows operating system on the new image.

### 7. Install Organization Tools
#### The CI/CD tool installs the organization tools on the new image.

### 8. Install Required Software
#### The CI/CD tool installs the required software applications on the new image.

### 9. Apply Security Hardening
#### The CI/CD tool applies security configurations and patches to the image using the Security Hardening participant.

### 10. Build and Test Image
#### The CI/CD tool builds and tests the final image to ensure it is ready for deployment.

### 11. Upload Image to Repository
#### The CI/CD tool uploads the final image to the Image Repository participant.

### 12. Provide Image for VDI Deployment
#### The Image Repository participant provides the final image to the VDI Teams participant for deployment to VDI environments.