# Dockerfile

目录结构(单Linux用户）：

/home/
├── docker-admin/               # Docker 管理文件
│   ├── dockerfiles/            # 存放所有 Dockerfile
│   │   ├── user1.Dockerfile    # 用户1的 Dockerfile
│   │   ├── user2.Dockerfile    # 用户2的 Dockerfile
│   │   └── pytorch-base.Dockerfile  # 基础镜像 Dockerfile
│   └── docker-compose.yml      # 统一管理多容器（可选）
│
├── shared/                     # 宿主机共享文件夹（所有容器可访问）
│   ├── ro-share/               # 只读共享（容器可读，不可写）
│   └── rw-share/               # 可读写共享（容器可读可写）
│
├── user1/                      # 用户1的专属目录
│   ├── code/                   # 用户1的代码（挂载到容器）
│   └── data/                   # 的数据集（挂载到容器）
│
└── user2/                      # 用户2的专属目录
    ├── code/                   # 用户2的代码
    └── data/                   # 用户2的数据集

初始化目录结构：

```sh
#!/bin/bash

# Docker directory structure setup script

# Set the base directory
BASE_DIR="/home/karyou/Dockers"

echo "Setting up Docker directory structure in $BASE_DIR..."

# Create Docker management directories
echo "Creating Docker admin directories..."
mkdir -p "$BASE_DIR"/docker-admin/dockerfiles
mkdir -p "$BASE_DIR"/shared/{ro-share,rw-share}
mkdir -p "$BASE_DIR"/user1/{code,data}
mkdir -p "$BASE_DIR"/user2/{code,data}

# Create Docker configuration files
echo "Creating Docker configuration files..."
touch "$BASE_DIR"/docker-admin/dockerfiles/user1.Dockerfile
touch "$BASE_DIR"/docker-admin/dockerfiles/user2.Dockerfile
touch "$BASE_DIR"/docker-admin/dockerfiles/pytorch-base.Dockerfile
touch "$BASE_DIR"/docker-admin/docker-compose.yml

# Set permissions
echo "Setting directory permissions..."
chmod 755 "$BASE_DIR"/shared/ro-share   # Read-only shared directory
chmod 777 "$BASE_DIR"/shared/rw-share   # Read-write shared directory
chmod 700 "$BASE_DIR"/user1/{code,data} # User1 private directories
chmod 700 "$BASE_DIR"/user2/{code,data} # User2 private directories

# Display final structure
echo -e "\nDirectory structure created:"
tree -L 3 "$BASE_DIR"

echo -e "\nSetup complete!"
```

