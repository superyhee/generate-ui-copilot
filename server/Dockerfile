# 使用官方 Node 镜像作为基础镜像，使用 alpine 版本
FROM node:18.17.0-alpine

# 设置工作目录
WORKDIR /app

# 拷贝 package.json 和 package-lock.json 到工作目录
COPY package*.json ./

# 安装依赖
RUN npm install --legacy-peer-deps 

# 安装 git
RUN apk update && apk add --no-cache git

# 初始化 git 仓库
RUN git init

# 配置 git 用户信息
RUN git config --global user.email "frontend@user.com"
RUN git config --global user.name "Docker"

# git add && git commit
RUN git add .
RUN git commit -m "init"

# 拷贝所有源代码到工作目录
COPY . .

# 暴露端口
EXPOSE 3001



# 运行应用
CMD ["node", "index.js"]