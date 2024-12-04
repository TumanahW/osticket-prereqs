<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [ Part I - Create Resource Group & Virtual Machine ](https://www.loom.com/share/e93d55f32ab049b1888146da8e4c8aa0?sid=562dbd42-8cda-4f88-8702-df73933c5f97)
- ### [ Part II - Install and Configure osTicket](https://www.loom.com/share/2adc36a3443d4330a4c6fef6eb16d0dc?sid=259dd574-a12e-4c64-8aa0-fd5b3bd92a01)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>
<ol>
 <li>Active Azure Subscription: Ensure your Azure account is set up to create and manage Virtual Machines. </li>
  <li>Virtual Machine Configuration: Deploy a Linux or Windows VM with at least 2 vCPUs and 4 GB RAM. Ensure HTTP/HTTPS ports are open for web access.</li>
  <li>Operating System: Windows (e.g., Server 2019 or Windows 10). </li>
  <li>Web Server: Install a web server IIS (Windows) to host the osTicket application.</li>
  <li>PHP Environment: Install PHP 7.4 or higher with required extensions (mysqli, mbstring, gd).</li>
  <li>Database Server: Install MySQL or MariaDB and set up a database with a user for osTicket. </li>
  <li>osTicket Installation Package: Download the osTicket zip file from the <a href="https://osticket.com/download" target="_blank">osTicket Official Website</a>, extract it to the web root, and set necessary file permissions.</li>
</ol>

<h2>Installation Steps</h2>

<h3> Log on to Microsoft Azure </h3>
<p>Log in to the Azure Portal: Go to https://portal.azure.com.</p>

![image](https://github.com/user-attachments/assets/8fd429db-3f58-4751-bc18-927fdd312946)

<br />

<p> Within the Microsoft Azure Portal create a Resource Group. A rescource group is a logical container that holds Azure Related Resources such as Virtal machines and storage accounts. It allows for us to manage them from a single unit. We will later use this  Resource group when we create our Virtual Machine. </p>

![image](https://github.com/user-attachments/assets/e327845f-a30d-4e22-808c-ef317cb2b0d2)

<br />

<p> Next, create a virtual machine(VM) with Windows 10 Pro, version 22H2.  you must create a virtual machine that has at least 2vcpus and 16gbs of memory. </p>
<p>Complete the following fields when you create the VM:
 <li>Name the VM </li>
 <li>Region  </li>
 <li>Availability Zone </li>
  <li> image: Windows 10 & Size: 2Vcpus</li>
  <li> Create a username and password that you will use to log into your virtual machine</li>
 <li>Check the licensing box at the bottom</li>
</p>

![image](https://github.com/user-attachments/assets/c2b5e986-8bf8-4e63-b850-577e2a683884)

<br />
<p>Go to the main page on the Azure portal > Search for Virtual Machine > Locate the virtual machine you just create and copy the public IP Address of the Virtual Machine.</p>

![image](https://github.com/user-attachments/assets/72cc8287-755d-47f8-b78c-b7df8e129e55)
<br />
<p>To access you're virtual machine you will need a Remote Desktop Application that you can log into. If you are using Mac as a local system, you can download it from the app store. If you are using Windows Os you can access Remote Desktop by going to Start> Settings > Systems> Remote Desktop. </p>


![image](https://github.com/user-attachments/assets/b381e89e-8d91-4b20-8fb0-e15b85d64be1)

![image](https://github.com/user-attachments/assets/615fe7a7-6dd3-47aa-ac8d-917856bb94e8)
 
 <br/>

<h2>Install  osTicket  and Configure</h2>

<p> Download the needed files from OsTicket's Website to the Desktop. Once Downloaded,extract the files.</p>

<img width="721" alt="Screenshot 2024-12-01 at 1 20 16 PM" src="https://github.com/user-attachments/assets/fecbea33-24ea-4ac4-8900-76a795037d2d">

<img width="712" alt="Screenshot 2024-12-01 at 1 20 46 PM" src="https://github.com/user-attachments/assets/966a50ad-1dd7-4109-8389-88a9c6c3b939">

<img width="717" alt="Screenshot 2024-12-01 at 1 21 10 PM" src="https://github.com/user-attachments/assets/e94fae49-c012-4621-990e-aef43c97616f">

<img width="719" alt="Screenshot 2024-12-01 at 1 21 32 PM" src="https://github.com/user-attachments/assets/783c453c-d772-4219-bdf4-56cf81306ac6">

<p> Next, We'll install and enable Information Internet Services(IIS) in Windows with CGI.osTicket, being a web-based ticketing system, requires a web server to host its files and manage HTTP requests.
 To enable IIS go to: control Panel> Click on Uninstall a program> On the left side bar click "Turn windows features on or off </p>

<img width="653" alt="Screenshot 2024-12-01 at 1 41 36 PM" src="https://github.com/user-attachments/assets/c688e3fc-6688-473a-8a61-5636f26ba728">
<img width="641" alt="Screenshot 2024-12-01 at 1 42 02 PM" src="https://github.com/user-attachments/assets/ccf8ec8e-f96c-4f36-9b08-1bfbb0c37fd3">
<img width="652" alt="Screenshot 2024-12-01 at 1 42 30 PM" src="https://github.com/user-attachments/assets/993396d2-5d1d-4c1f-a34a-ba916ea8eca8">
<img width="647" alt="Screenshot 2024-12-01 at 1 42 54 PM" src="https://github.com/user-attachments/assets/f4f277ed-9394-490b-b6b4-f55b2c6b3b68">
<img width="629" alt="Screenshot 2024-12-01 at 8 46 09 PM" src="https://github.com/user-attachments/assets/db227b22-ee69-4e1c-8a5c-8823d2679da3">
<img width="650" alt="Screenshot 2024-12-01 at 8 46 37 PM" src="https://github.com/user-attachments/assets/8362a62f-9ad6-4f64-82ea-2cc10122e2ce">
<img width="621" alt="Screenshot 2024-12-01 at 8 47 18 PM" src="https://github.com/user-attachments/assets/f5a2c051-f5bd-4766-bc10-14a8c9f7ef00">
</br>
<p> Next, We will install PHP Manager.PHP Manager simplifies managing PHP settings and extensions on IIS, ensuring compatibility and proper configuration for osTicket. </p>

![Screenshot 2024-12-02 at 10 39 54 PM](https://github.com/user-attachments/assets/bb1bcf7f-bd0f-4513-901a-108d90b60cb0)

![Screenshot 2024-12-02 at 10 44 58 PM](https://github.com/user-attachments/assets/f4f5d319-f067-409c-932a-3f52d4ae3504)

![Screenshot 2024-12-02 at 10 45 39 PM](https://github.com/user-attachments/assets/db4a85a5-d8fa-4991-9193-d789f4b6907a)

![Screenshot 2024-12-02 at 10 46 19 PM](https://github.com/user-attachments/assets/50908885-e6e1-4e23-a865-c6dc3b7b610e)

![Screenshot 2024-12-03 at 9 32 04 PM](https://github.com/user-attachments/assets/a21ccf58-a837-498d-93c7-e4a028b0dc5e)
<p>Next, We'll extract PHP files to the PHP folder we created on the C:/drive.</p>
![Screenshot 2024-12-03 at 9 35 47 PM](https://github.com/user-attachments/assets/5e88bcda-6dfa-460b-a6d6-0c5e6bc1438a)

![Screenshot 2024-12-03 at 9 37 14 PM](https://github.com/user-attachments/assets/1dfc1cb6-9ab2-46c0-88a9-5f0cbccd3bff)

![Screenshot 2024-12-03 at 9 37 57 PM](https://github.com/user-attachments/assets/b8b74866-78cd-4c4b-a394-72f566296e05)
![Screenshot 2024-12-03 at 9 40 57 PM](https://github.com/user-attachments/assets/624d7b2e-86f2-4089-bd37-ace195a64202)

![Screenshot 2024-12-03 at 9 44 42 PM](https://github.com/user-attachments/assets/94da47ad-974a-4c32-816f-deffb8004169)
![Screenshot 2024-12-03 at 9 45 28 PM](https://github.com/user-attachments/assets/709091c1-9d98-409b-a57f-b58fb6e99396)

![Screenshot 2024-12-03 at 9 55 55 PM](https://github.com/user-attachments/assets/e23a1fc0-7429-4132-95a1-7f48bbf85bc9)

![Screenshot 2024-12-03 at 9 56 43 PM](https://github.com/user-attachments/assets/8dc044a8-a9f7-41b9-899d-756a8a8387a8)
![Screenshot 2024-12-03 at 9 57 47 PM](https://github.com/user-attachments/assets/d724af5a-ca1f-4fee-a0a6-dca41220e15c)
![Screenshot 2024-12-03 at 9 58 09 PM](https://github.com/user-attachments/assets/4c9b5b56-381e-48fd-97f8-0a4526d7fabb)
![Screenshot 2024-12-03 at 9 58 35 PM](https://github.com/user-attachments/assets/b2917d8b-1afb-404c-a5b9-b415c2749f89)
![Screenshot 2024-12-03 at 9 59 00 PM](https://github.com/user-attachments/assets/3c560916-5f31-48d9-908f-a1a662106bdd)
<p>39 - VC-REDIS</p>

![Screenshot 2024-12-03 at 10 10 51 PM](https://github.com/user-attachments/assets/22969c25-842f-4320-831f-56847afce67e)

<p>We'll install MySQL</p>

![Screenshot 2024-12-03 at 10 13 11 PM](https://github.com/user-attachments/assets/8fd9c670-360f-406d-a013-a1b06c239e6f)
![Screenshot 2024-12-03 at 10 15 26 PM](https://github.com/user-attachments/assets/d482b198-98cd-446b-8c38-107328a5fb0a)







