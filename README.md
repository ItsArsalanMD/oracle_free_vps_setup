# Oracle Cloud Free VPS Setup Guide (Always Free)

## Step 1: Create Oracle Cloud Account

-   Go to https://www.oracle.com/cloud/free/
-   Click **Start for free**
-   Complete email, phone, and card verification

------------------------------------------------------------------------

## Step 2: Login to OCI Dashboard

-   Open https://cloud.oracle.com/
-   Navigate to **Compute → Instances**
-   Click **Create Instance**

------------------------------------------------------------------------

## Step 3: Configure Instance

**Name:**

    youtube-automation-server

**Image:** - Ubuntu 22.04

------------------------------------------------------------------------

## Step 4: Select Shape (IMPORTANT)

Click **Change Shape**

Choose: - VM.Standard.A1.Flex (Recommended) - 2 CPU - 12 GB RAM

OR

-   VM.Standard.E2.1.Micro

⚠️ Must show: **Always Free Eligible**

------------------------------------------------------------------------

## Step 5: Networking

-   Keep default settings
-   Public IP: Enabled

------------------------------------------------------------------------

## Step 6: SSH Key

-   Select: Generate Key Pair
-   Download private key (.pem)

------------------------------------------------------------------------

## Step 7: Boot Volume

-   Default (\~47GB)
-   Must be Always Free Eligible

------------------------------------------------------------------------

## Step 8: Create Instance

-   Click Create
-   Wait 1--2 minutes

------------------------------------------------------------------------

## Step 9: Connect via SSH

    ssh -i your-key.pem ubuntu@your-public-ip

------------------------------------------------------------------------

## Step 10: Initial Setup

    sudo apt update && sudo apt upgrade -y
    sudo apt install -y git curl unzip

------------------------------------------------------------------------

## Step 11: Open Ports

Go to Networking → Security List: - Allow ports 22, 80, 443

------------------------------------------------------------------------

## Step 12: Setup Cron Job

    crontab -e

Example:

    0 10 * * * /usr/bin/node /home/ubuntu/upload.js

------------------------------------------------------------------------

## Important Notes

### VPS Runs Forever If:

-   Using Always Free resources
-   Within limits

### VPS May Stop If:

-   Idle for long time

Keep-alive script:

    while true; do echo "running"; sleep 300; done

------------------------------------------------------------------------

## Final Outcome

-   24/7 Free VPS
-   Automated cron jobs
-   No 30-day expiration
