# osTicket_Pre<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png"/>
</p>

# Installing osTicket: Prerequisites and Setup

This guide provides a step-by-step walkthrough for setting up osTicket, a powerful help desk ticketing system. Follow the instructions below to ensure a smooth installation process.

---

## Tools and Technologies Used

- **Operating Systems**: Windows 10 (Build 19044)
- **Platforms**: Microsoft Azure (Virtual Machines), Remote Desktop Protocol (RDP)
- **Software**: Internet Information Services (IIS), PHP Manager, MySQL, HeidiSQL, osTicket
- **Dependencies**: Microsoft Visual C++ Redistributable

---

## Overview of Steps

1. **Create and Configure Azure Virtual Machine**
   - Set up a Windows 10 VM with required specifications on Azure.
   - Connect to the VM via Remote Desktop.

2. **Install Internet Information Services (IIS)**
   - Enable IIS and required application development features.

3. **Install PHP Manager and Required Modules**
   - Download and set up PHP Manager and Rewrite Module.

4. **Configure PHP Environment**
   - Create a PHP directory and extract the PHP package.
   - Install Visual C++ Redistributable.

5. **Install and Configure MySQL and HeidiSQL**
   - Set up MySQL and create a new database using HeidiSQL.

6. **Install and Configure osTicket**
   - Extract osTicket files and configure required PHP extensions.

7. **Complete osTicket Setup**
   - Run the osTicket installation wizard and finalize configurations.

8. **Perform Post-Installation Tasks**
   - Remove the setup directory and secure configuration files.

---

## Prerequisites

1. Create a Virtual Machine (VM) in Azure.
2. Install necessary software and dependencies:
   - osTicket v1.15.8
   - HeidiSQL
   - MySQL
   - PHP
   - Microsoft Visual C++ Redistributable

---

## Installation Steps

### Step 1: Set Up Azure Virtual Machine

- **Create Resource Group and VM**:
  - In Azure, create a Resource Group.

<p align="center">
<img src="https://i.imgur.com/eBi5k2l.png" height="75%" width="100%"/>
</p>

- **Create a VM on Azure**:
  - Set up a Windows 10 VM with 2-4 virtual CPUs and a new Virtual Network (Vnet).
  - Note down the username and password for RDP access.

<p align="center">
<img src="https://i.imgur.com/dEF1c7h.png" height="75%" width="100%"/>
</p>

- **Connect via Remote Desktop**:
  - Use the Remote Desktop Connection app to log into your Azure VM.

### Step 2: Enable IIS

- Navigate to **Control Panel > Programs > Turn Windows features on or off**.
- Enable **Internet Information Services (IIS)** and expand the following options:
  - **World Wide Web Services > Application Development Features > CGI**

<p align="center">
<img src="https://i.imgur.com/iB0DDRd.png" height="75%" width="100%"/>
</p>
<p align="center">
<img src="https://i.imgur.com/1RmIXB7.png" height="75%" width="100%"/>
</p>

### Step 3: Install PHP Manager and Rewrite Module

- Download and install the **PHP Manager** and **Rewrite Module**. You can find the files used on [here](https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) 📁

<p align="center">
<img src="https://i.imgur.com/pmwpPEu.png" height="75%" width="100%"/>
</p>

### Step 4: Configure PHP

- **Create PHP Directory**:
  - Create a folder `C:\PHP`.
  - Download and extract the `php-7.3.8-nts-Win32-VC15-x86.zip` file into `C:\PHP`.

<p align="center">
<img src="https://i.imgur.com/18746085-a3cf-4f1f-b0d5-5cd73f969319.png" height="75%" width="100%"/>
</p>

- **Install VC Redistributable**:
  - Download and install **VC_Redist**.

<p align="center">
<img src="https://i.imgur.com/Gx8ryBV.png" height="75%" width="100%"/>
</p>

### Step 5: Install MySQL and HeidiSQL

- Download and install **MySQL**.
  - Set up a username and password for database access.

<p align="center">
<img src="https://i.imgur.com/IVpLg40.png" height="75%" width="100%"/>
</p>

- Install **HeidiSQL** and create a new database named `osTicket`.

<p align="center">
<img src="https://i.imgur.com/vXzmQqg.png" height="75%" width="100%"/>
</p>

### Step 6: Install osTicket

- Download osTicket and extract the `upload` folder to `C:\inetpub\wwwroot`.
- Rename `upload` to `osTicket`.

<p align="center">
<img src="https://i.imgur.com/pDikkgq.png" height="75%" width="100%"/>
</p>

- Restart IIS and browse to the osTicket installation page (`http://localhost/osTicket`).

### Step 7: Configure osTicket

- Enable required PHP extensions in IIS:
  - `php_imap.dll`
  - `php_intl.dll`
  - `php_opcache.dll`

<p align="center">
<img src="https://i.imgur.com/LFKo5Hs.png" height="75%" width="100%"/>
</p>

- Rename and set permissions for the configuration file:
  - Rename `ost-sampleconfig.php` to `ost-config.php`.
  - Disable inheritance and assign `Everyone` full access.

<p align="center">
<img src="https://i.imgur.com/YzsMXNX.png" height="75%" width="100%"/>
</p>

### Step 8: Complete Installation

- Configure the database in the osTicket setup wizard:
  - Database Name: `osTicket`
  - Username: `root`
  - Password: Set during MySQL installation.

<p align="center">
<img src="https://i.imgur.com/akDyber.png" height="75%" width="100%"/>
</p>

- Click **Install Now!** to finalize.

### Step 9: Post-Installation Cleanup

- Delete the `setup` directory: `C:\inetpub\wwwroot\osTicket\setup`.
- Set `ost-config.php` to read-only.

<p align="center">
<img src="https://i.imgur.com/n6k46XL.png" height="75%" width="100%"/>
</p>

### Step 10: Access osTicket Admin Panel

- Log in to the osTicket Admin Panel: `http://localhost/osTicket/scp/login.php`.

<p align="center">
<img src="https://i.imgur.com/8wvWH0H.jpg" height="75%" width="100%"/>
</p>

---

## Congratulations!

You've successfully installed and configured osTicket.
