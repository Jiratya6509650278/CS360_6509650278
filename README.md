# STRAPI

## **Strapi**

**Strapi** เป็น Headless CMS (Content Management System) แบบโอเพ่นซอร์ส ที่พัฒนาด้วย Node.js สำหรับสร้างและจัดการเนื้อหาเว็บไซต์หรือแอปพลิเคชันต่าง ๆ โดยไม่ผูกติดกับการแสดงผลบน Frontend แบบใดแบบหนึ่งเพียงอย่างเดียว ซึ่งช่วยนักพัฒนาในการสร้างแอปพลิเคชันที่สามารถจัดการเนื้อหาได้สะดวก

## วัตถุประสงค์ของ Strapi
 -   **Headless CMS** Strapi ช่วยแยกการจัดการเนื้อหาออกจากส่วนของ Frontend  ทำให้สามารถส่งเนื้อหาไปยังอุปกรณ์ใด ๆ ก็ได้ผ่าน API (เช่น RESTAPI หรือ GraphQL)
 -   **Customizable API** นักพัฒนาสามารถสร้าง API ที่กำหนดเองได้ เพื่อให้ตรงกับความต้องการของโปรเจกต์ 
 - **Content Management** มีเครื่องมือที่ใช้ในการจัดการเนื้อหาผ่านแดชบอร์ดที่ผู้ใช้สามารถเข้าถึงได้
## กรณีการใช้งาน (Use Cases) ของ Strapi
-   **การจัดการเนื้อหาสำหรับ Mobile App** Headless CMS ของ Strapi สามารถให้บริการเนื้อหาผ่าน API ไปยังแอปพลิเคชันบนมือถือได้หลายแพลตฟอร์ม ทำให้ช่วยในการจัดการเนื้อหาสำหรับเว็บไซต์และแอปบนมือถือ
-   **การจัดการเนื้อหาสำหรับ eCommerce** Strapi สามารถใช้ในการจัดการสินค้าหรือเนื้อหาที่เกี่ยวข้องกับการขายสินค้าออนไลน์ เช่น จัดการสินค้า หมวดหมู่ และข้อมูลที่เกี่ยวข้องกับสินค้า

## องค์ประกอบหลักของ Strapi

 - **Admin Panel:** ส่วนติดต่อผู้ใช้สำหรับการจัดการเนื้อหาและการตั้งค่าระบบ
 -  **Content-Types Builder:** เครื่องมือสำหรับสร้างและกำหนดโครงสร้างข้อมูล
 -  **Roles & Permissions:** ระบบจัดการสิทธิ์และการเข้าถึง
 -  **Media Library:** ระบบจัดการไฟล์มีเดีย
 -  **API Generator:** สร้าง API โดยอัตโนมัติ
 -  **Plugin System:** ระบบปลั๊กอินสำหรับเพิ่มฟังก์ชันการทำงาน
 -  **Database Connectors:** ใช้รองรับการเชื่อมต่อกับฐานข้อมูล
 -  **Authentication:** ระบบยืนยันตัวตนและการจัดการผู้ใช้

## ขั้นตอนการติดตั้งของ Strapi

**1. เตรียมเครื่องก่อน Install**

-   **NodeJS.**  v.18 หรือ v.20
- **NPM** มากกว่า v.6
-  **Python** ถ้าเราใช้ SQLite database
- **Folder** สร้างโฟลเดอร์สำหรับที่จะโหลดไฟล์ Strapi ไว้

**2. เปิด Terminal ของเครื่องเราขึ้นมา**
	ใช้คำสั่ง **cd** เข้าไฟล์ที่เราต้องการ
**3. ดาวน์โหลด strapi**
ใช้คำสั่งตามด้านล่างนี้ 

    npx create-strapi-app@latest my-project
 **4. เลือก Quickstart** 
เลือก Login หรือ Skip 
**5. รอจนติดตั้งสำเร็จ จะขึ้นให้สร้าง Account**
กรอกข้อมูลของเราให้เรียบร้อย
**6. สามารถใช้งาน Strapi ได้แล้ว**
 เปิดใช้งาน Strapi ด้วยคำสั่งดังนี้ 

    npm  run  develop

## **.gitignore**

  ไฟล์ที่ใช้สำหรับบอก Git ว่าควรจะเพิกเฉย (ignore) ไฟล์หรือโฟลเดอร์ใดบ้างในโปรเจกต์ของคุณเมื่อทำการ commit หรือ push ไปยัง repository การที่เราต้องการ ignore  มีเหตุผลดังนี้
  -   **ป้องกันไม่ให้ข้อมูลที่เป็นส่วนตัวถูก push ขึ้น repository**: เช่น คีย์ API, ไฟล์การตั้งค่าเฉพาะที่ควรอยู่ในเครื่องผู้พัฒนาเท่านั้น
-   **ป้องกันไฟล์ที่ไม่จำเป็นถูกเก็บใน version control**: เช่น ไฟล์ที่ถูก generate ขึ้นมาโดยอัตโนมัติหรือไฟล์ที่ใหญ่เกินไป

## Deployment Starpi
**1.Launch EC2 Instances on AWS**
เข้าไปสร้างและตั้งค่า Instance บน AWS
โดยตั้งค่าตามด้านล่างนี้
 1.   **Instance Type**  
t2.small
 2.   **Security Group**
    -   **Type:**  `SSH`,  **Protocol:**  `TCP`,  **Port Range**  `22`,  **Source:**  `::/0`
    -   **Type:**  `HTTP`,  **Protocol:**  `TCP`,  **Port Range**  `80`,  **Source:**  `0.0.0.0/0, ::/0`
    -   **Type:**  `HTTPS`,  **Protocol:**  `TCP`,  **Port Range**  `443`,  **Source:**  `0.0.0.0/0, ::/0`
    -   **Type:**  `Custom TCP Rule`,  **Protocol:**  `TCP`,  **Port Range**  `1337`,  **Source:**  `0.0.0.0/0`
หลังจากนั้นกด Launch Instances

**2. เปิด terminal แล้ว copy  SSH วางเพื่อเข้าสู่ instances**
cd เข้าสู่ Folder ของเราที่มี Key pair อยู่ด้วย
**3.อัพเดต ติดตั้ง Nodejs. และตั้งค่า**
3.1   sudo yum update
 3.2    sudo yum install curl -y
 3.3 สร้าง npm default directory
3.4 cd ~
3.5 mkdir ~/.npm-global
 3.6 npm config set prefix '~/.npm-global' 
 **4. สร้าง Path ให้ Directory ไป Node_modules** 
  4.1 sudo nano ~/.profile
 4.2 export PATH=~/.npm-global/bin:$PATH 
 4.3 source ~/.profile
 **5. ติดตั้ง  Git** 
 sudo yum install git -y
 **6. ใช้ git clone URL  Github reporitory ของเรา**
 **7. cd เข้าโปรเจ็คที่ clone มา**
7.1 npm install
7.2 NODE_ENV=production npm run build
 **8. ติดตั้ง  PM2 Runtime + สร้าง แก้ไข 	environment config**
 8.1 npm install pm2@latest -g
 8.2 cd ~
8.3 pm2 init
8.4 sudo nano ecosystem.config.js
8.5 แก้ไข config โดยพิมพ์ตามนี้ set ค่าตามไฟล์ .env ในเครื่องของเรา

    module.exports = {
      apps: [
        {
          name: 'your-app-name', // Your project name
          cwd: '/home/ubuntu/my-project', // Path to your project
          script: 'npm', // For this example we're using npm, could also be yarn
          args: 'start', // Script to start the Strapi server, `start` by default
          env: {
            APP_KEYS: 'your app keys', // you can find it in your project .env file.
            API_TOKEN_SALT: 'your api token salt',
            ADMIN_JWT_SECRET: 'your admin jwt secret',
            JWT_SECRET: 'your jwt secret',
            NODE_ENV: 'production',
            DATABASE_HOST: 'your-unique-url.rds.amazonaws.com', // database Endpoint under 'Connectivity & Security' tab
            DATABASE_PORT: '5432',
            DATABASE_NAME: 'strapi', // DB name under 'Configuration' tab
            DATABASE_USERNAME: 'postgres', // default username
            DATABASE_PASSWORD: 'Password',
            AWS_ACCESS_KEY_ID: 'aws-access-key-id',
            AWS_ACCESS_SECRET: 'aws-access-secret', // Find it in Amazon S3 Dashboard
            AWS_REGION: 'aws-region',
            AWS_BUCKET_NAME: 'my-project-bucket-name',
          },
        },
      ],
    };
  **9. ใช้คำสั่งรัน PM2**
pm2 startup systemd
**10. Copy command ที่ขึ้นมา** 
sudo  env  PATH=$PATH:/usr/bin /usr/lib/node_modules/pm2/bin/pm2 startup systemd -u your-name --hp /home/your-name (commarn แบบนี้)
**11.  Save Pm2**
pm2 save
**12.  เมื่อจะรัน Strapi Project อีกครั้ง สามารถใช้คำสั่งดังนี้ได้เลย**
npm start

**

## Reference
Strapi : https://docs.strapi.io/
