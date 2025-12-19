# Runbook: Troubleshooting EC2 SSH Connection Issues

**Scenario:** A user reports they cannot connect to their Linux EC2 instance via SSH.

### Step 1: Check Instance State
- Verify the instance is in the `Running` state in the AWS Console.
- Check the **Status Checks** tab. If "System Status Check" is failing, it may be a hardware issue (try stopping and starting the instance).

### Step 2: Verify Security Group Rules
- Ensure there is an **Inbound Rule** allowing **SSH (Port 22)**.
- Check the **Source**: Is it set to `0.0.0.0/0` (Public) or a specific IP? If it's a specific IP, ensure the user's current IP matches.

### Step 3: Check Network Access (VPC/Subnet)
- Does the instance have a **Public IP** address?
- Is the subnet associated with an **Internet Gateway** via the Route Table?

### Step 4: Key Pair Verification
- Confirm the user is using the correct `.pem` file that matches the key pair assigned to the instance at launch.
- Ensure file permissions on the key are correct: `chmod 400 my-key.pem`.

---
*Created by d-rich-cloud as part of AWS Support training.*
