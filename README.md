1. สร้าง Dockerfile โดยใน file ประกอบไปด้วย
```Dockerfile
FROM oven/bun
COPY . .
RUN bun install
CMD ["bun", "run", "start"]
```

2. build container โดยใช้
```bash
sudo docker build -t bun1 .
```

3. run container โดยการ map port 80 ของเครื่อง server กับ port 3000 ภายใน container โดยใช้
```bash
sudo docker run -d -p 80:3000 bun1
```
