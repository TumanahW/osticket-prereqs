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
![Screenshot 2024-12-03 at 10 13 11 PM](https://github.com/user-attachments/assets/8fd9c670-360f-406d-a013-a1b06c239e6f)

![Screenshot 2024-12-03 at 10 15 26 PM](https://github.com/user-attachments/assets/d482b198-98cd-446b-8c38-107328a5fb0a)
<p>We'll install MySQL</p>

![Screenshot 2024-12-03 at 10 22 14 PM](https://github.com/user-attachments/assets/3da606c2-9b07-49c5-b02b-cd7d1485d238)
![Screenshot 2024-12-03 at 10 15 35 PM](https://github.com/user-attachments/assets/be5fd44c-f299-4028-bb56-57cc50487b70)

![Screenshot 2024-12-03 at 10 36 25 PM](https://github.com/user-attachments/assets/5edd5ef1-d770-4c4d-b641-0d08248a8ef4)

![Screenshot 2024-12-03 at 10 38 20 PM](https://github.com/user-attachments/assets/13c419bb-83b0-4c41-8627-3aa6004ae004)
![Screenshot 2024-12-03 at 10 38 50 PM](https://github.com/user-attachments/assets/44997003-2290-480c-8f04-37dc0b294f18)
![Screenshot 2024-12-03 at 10 39 13 PM](https://github.com/user-attachments/assets/70db1b96-fe3d-4b74-834d-346166abc87e)
![Screenshot 2024-12-03 at 10 39 40 PM](https://github.com/user-attachments/assets/05a99e42-7a54-40e5-986d-299b1621e64c)
![Screenshot 2024-12-03 at 10 40 15 PM](https://github.com/user-attachments/assets/6021a856-6017-4d07-b4f3-b5d111504a4b)
![Screenshot 2024-12-03 at 10 41 15 PM](https://github.com/user-attachments/assets/a5b8379b-898b-4b50-8ec4-40dbf1ada0e9)

<p> Next, we'll configure PHP with in our webserver.</p>

![Screenshot 2024-12-03 at 10 42 41 PM](https://github.com/user-attachments/assets/d1af9b23-6a95-4272-83ff-2edf438c0a67)
![Screenshot 2024-12-03 at 10 43 37 PM](https://github.com/user-attachments/assets/c4cde7ca-127c-404f-888a-0b3a5219e973)
![Screenshot 2024-12-03 at 10 43 37 PM](https://github.com/user-attachments/assets/ba700867-95f6-44a4-9faa-eab7a4e0f0b3)
![Screenshot 2024-12-03 at 10 44 40 PM](https://github.com/user-attachments/assets/cee4691e-b5d4-4cc4-b956-9ff4d266ea33)
![Screenshot 2024-12-03 at 10 50 29 PM](https://github.com/user-attachments/assets/5ef0510b-366e-45fc-934a-18f1aee82003)
![Screenshot 2024-12-03 at 10 51 32 PM](https://github.com/user-attachments/assets/3b99b648-633d-4d66-8647-a55e0963a705)
![Screenshot 2024-12-03 at 10 52 59 PM](https://github.com/user-attachments/assets/748f2789-a478-4668-937e-008a623299a7)
![Screenshot 2024-12-03 at 10 53 31 PM](https://github.com/user-attachments/assets/ceac6145-eff5-40de-8e68-c831c59d28d5)
![Screenshot 2024-12-03 at 10 58 08 PM](https://github.com/user-attachments/assets/c345869c-f30d-486b-96f5-0c93c3d2e086)
![Screenshot 2024-12-03 at 10 58 55 PM](https://github.com/user-attachments/assets/0487fb77-5c9d-44c7-982c-5ab859eec4d8)
![Screenshot 2024-12-03 at 10 59 20 PM](https://github.com/user-attachments/assets/ad99d10c-d911-4154-88ff-84472552a7a7)
![Screenshot 2024-12-03 at 10 59 45 PM](https://github.com/user-attachments/assets/8c044e78-b0c5-466c-8210-c0ee8df13387)
![Screenshot 2024-12-03 at 11 00 40 PM](https://github.com/user-attachments/assets/1fbaa578-d36d-4399-bbb9-cdd55e373fa4)
![Screenshot 2024-12-03 at 11 01 25 PM](https://github.com/user-attachments/assets/78c8a879-28bd-4559-9926-022ddfcb6efd)
![Screenshot 2024-12-03 at 11 02 15 PM](https://github.com/user-attachments/assets/0ec32d7b-5b37-47d7-8e02-930b000a5d75)
![Screenshot 2024-12-03 at 11 12 57 PM](https://github.com/user-attachments/assets/c5336363-ba94-4d59-9de4-a32da792dc96)

![Screenshot 2024-12-03 at 11 18 02 PM](https://github.com/user-attachments/assets/0eb643f9-cd4a-4c45-b798-8f3e49f87b57)
![Screenshot 2024-12-03 at 11 18 30 PM](https://github.com/user-attachments/assets/37e29845-d788-461c-9742-3b3044ef255f)
![Screenshot 2024-12-03 at 11 18 55 PM](https://github.com/user-attachments/assets/cb2d1106-d5c2-461f-9f36-4202400e6ebd)
![Screenshot 2024-12-03 at 11 19 23 PM](https://github.com/user-attachments/assets/b0ad07a0-cd9f-48bc-a4e8-dfec96f8d6de)
![Screenshot 2024-12-03 at 11 20 00 PM](https://github.com/user-attachments/assets/74e0ca5a-055e-49cb-ab81-cf3ca35e1c85)
![Screenshot 2024-12-03 at 11 27 17 PM](https://github.com/user-attachments/assets/7574ee2f-555d-4c99-bc75-67eefd2bb3d0)
![Screenshot 2024-12-03 at 11 28 06 PM](https://github.com/user-attachments/assets/f2a4fb02-f95e-4d11-8b04-a8d0845064b7)
![Screenshot 2024-12-03 at 11 28 24 PM](https://github.com/user-attachments/assets/bb572252-7ba6-4e00-a7fe-707f4796f52c)
![Screenshot 2024-12-03 at 11 28 43 PM](https://github.com/user-attachments/assets/5eeaa91f-eb48-4edb-be85-b10b8fea85dd)
![Screenshot 2024-12-03 at 11 29 20 PM](https://github.com/user-attachments/assets/105bf6a0-c62d-404a-9d30-13317b63319e)
![Screenshot 2024-12-03 at 11 29 46 PM](https://github.com/user-attachments/assets/37b1fb46-26cb-4555-a555-976a864616f3)
![Screenshot 2024-12-03 at 11 30 14 PM](https://github.com/user-attachments/assets/7ac035a7-c8df-44e4-88bc-fb30797e9c89)
![Screenshot 2024-12-03 at 11 30 49 PM](https://github.com/user-attachments/assets/2cb02e55-0a7b-4fc4-905c-bee00ed90f4f)
![Screenshot 2024-12-03 at 11 32 06 PM](https://github.com/user-attachments/assets/b595a4b4-2fec-4ebe-861f-8b472d129ad3)

![Screenshot 2024-12-03 at 11 35 45 PM](https://github.com/user-attachments/assets/62e939c0-a03f-41f7-9d3c-1d9736a161fb)
![Screenshot 2024-12-03 at 11 36 19 PM](https://github.com/user-attachments/assets/ff9d83df-56a4-474e-bfe1-872849498fcf)
![Screenshot 2024-12-03 at 11 38 48 PM](https://github.com/user-attachments/assets/8ba0ed15-abfc-4d57-8225-9670908e4ac0)
![Screenshot 2024-12-03 at 11 42 57 PM](https://github.com/user-attachments/assets/9c6b7b72-42a9-4162-a53f-a98e2e9957bc)
![Screenshot 2024-12-03 at 11 43 19 PM](https://github.com/user-attachments/assets/e2d7f9ce-a64c-4526-be4d-8a86dfaa3f17)
![Screenshot 2024-12-03 at 11 43 41 PM](https://github.com/user-attachments/assets/e3917508-4e05-419d-8551-3df8ff86401c)
![Screenshot 2024-12-03 at 11 44 09 PM](https://github.com/user-attachments/assets/594f459d-6659-49fc-8eb8-b9d43798b0ce)
![Screenshot 2024-12-03 at 11 44 28 PM](https://github.com/user-attachments/assets/171177e3-d057-43d7-96b7-1acc66426b07)
![Screenshot 2024-12-03 at 11 45 13 PM](https://github.com/user-attachments/assets/fdb90716-82d6-46c2-87a1-4d64c4c3293b)
![Screenshot 2024-12-03 at 11 46 40 PM](https://github.com/user-attachments/assets/04dabdd6-1397-4d02-9a6b-3597595f97d0)
![Screenshot 2024-12-03 at 11 47 09 PM](https://github.com/user-attachments/assets/89cba620-4677-43d7-9ec3-0532c7623183)

![Screenshot 2024-12-03 at 11 48 27 PM](https://github.com/user-attachments/assets/f038d5db-0e88-4636-b2a7-9f3b6b6cbd9c)
![Screenshot 2024-12-03 at 11 48 58 PM](https://github.com/user-attachments/assets/96bb4baa-33a0-4857-82e0-14bcc146de72)
![Screenshot 2024-12-03 at 11 50 03 PM](https://github.com/user-attachments/assets/ae03f519-d78d-4f19-90d4-3c3c710ee8d5)
![Screenshot 2024-12-03 at 11 50 39 PM](https://github.com/user-attachments/assets/aa19eb00-b8a8-4d22-a839-bd111e63bc86)
![Screenshot 2024-12-03 at 11 51 00 PM](https://github.com/user-attachments/assets/ae4cc14c-5682-4863-a8be-ebf81889127b)
![Screenshot 2024-12-03 at 11 52 01 PM](https://github.com/user-attachments/assets/74045f16-f130-47db-b552-3047c3ce5bd3)





