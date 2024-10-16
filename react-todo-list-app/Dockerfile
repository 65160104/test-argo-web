

# ใช้ภาพฐานของ Node.js
FROM node:18
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
CMD ["node", "server.js"]  # หรือคำสั่งที่ใช้ในการเริ่มต้นแอปพลิเคชัน

# สร้างเซิร์ฟเวอร์ Nginx สำหรับเสิร์ฟ Vue.js
FROM nginx:alpine
COPY --from=build-stage /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]