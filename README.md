1. สร้าง instant บน AWS และเชื่อมต่อเข้าไป
2. นำ file ของ web upload เข้า instant
3. สร้าง Dockerfile โดยใน file ประกอบไปด้วย
```Dockerfile
FROM oven/bun
COPY . .
RUN bun install
CMD ["bun", "run", "start"]
```

4. build container โดยใช้
```bash
sudo docker build -t bun1 .
```

5. run container โดยการ map port 80 ของเครื่อง server กับ port 3000 ภายใน container โดยใช้
```bash
sudo docker run -d -p 80:3000 bun1
```

IP ของ server
http://54.169.203.159/

