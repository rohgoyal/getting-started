# Installing Node.js and API Connect


### What you'll need
1. Node.js
2. Node Product Manager (NPM)
3. API Connect _Essentials_

<table>
  <tr><td><b>Node.js</b>: An asychronous event driven JavaScript runtime used to build and run scalable network applications
    <br>
    <b>Node Product Manager</b>: JavaScript package manager and software registry<br>
    <b>API Connect</b>: A free version of API Connect hosted on your laptop</td></tr>
  </table>  


### Install node.js
1. Download and install node.js from one of the two sources:
   * https://nodejs.org/en/download/  
      **OR**
   * https://developer.ibm.com/node/sdk/v6/  

    _Installing node.js also installs **npm** (Node Package Manager)_

2.  Update **npm**   
    In a command line, enter `npm install -g npm`   


3. Check the installed version and path
   ```
   APIC DEMO> node -v
   v6.10.3

   APIC DEMO> which node
   /usr/local/bin/node

   APIC DEMO> npm -v
   4.5.0

   APIC DEMO> which npm
   /usr/local/bin/npm

   APIC DEMO> echo $PATH
   /usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin/npm
   ```  


### Install the API Connect toolkit
1. Update the npm config to allow use of untrusted certificates  
   `npm config -g set strict-ssl false`  

2. Install the API Connect toolkit from **npm**  
    `npm install -g apiconnect`

3. Check the installed version  
    `apic -v`
