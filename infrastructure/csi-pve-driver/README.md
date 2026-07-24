# Create dedicated CSI role
pveum role add CSI -privs "VM.Audit VM.Config.Disk Datastore.Allocate Datastore.AllocateSpace Datastore.Audit"

# Create user and assign role
pveum user add kubernetes-csi@pve
pveum aclmod / -user kubernetes-csi@pve -role CSI

# Generate token without privilege separation
pveum user token add kubernetes-csi@pve csi -privsep 0

(Copy the generated value — this is your token_secret).

In the Infisical Web UI ([https://infisicial.datakube.org](https://infisicial.datakube.org)) Web
Navigate to your project (talos-8-r-ud), select the prod environment, and go to the path you specified (e.g., / or /proxmox).

Create a Single Secret where:
    Key Name: config.yaml
    Value Type: Multiline String / Raw Text
    Value Content:

clusters:
  - url: https://192.168.68.2:8006/api2/json
    insecure: true # Set to false if you use a trusted CA cert
    token_id: "kubernetes-csi@pve!csi"
    token_secret: "YOUR_PROXMOX_TOKEN_SECRET_HERE"
    region: "home-lab"
