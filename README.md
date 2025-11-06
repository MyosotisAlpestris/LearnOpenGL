# LearnOpenGL 学习项目

这是我学习 OpenGL 的练习项目。

## 项目结构

```
LearnOpenGL/
├── firstTriangle/       # 第一个三角形
│   ├── src/
│   │   └── triangle.cpp
│   └── CMakeLists.txt
└── README.md
```

## 依赖库

本项目需要以下库：
- **GLFW** - 窗口和输入管理
- **GLAD** - OpenGL 函数加载器

## 编译说明

### 方法 1: 使用默认相对路径

如果你的目录结构是：
```
Code/
├── Libraries/
│   ├── GLFW/
│   └── GLAD/
└── Practice/
    └── LearnOpenGL/
```

直接编译即可：
```bash
cd firstTriangle
mkdir build
cd build
cmake ..
cmake --build .
```

### 方法 2: 自定义库路径

如果你的库在其他位置，设置环境变量：

**Windows PowerShell:**
```powershell
$env:LIBS_PATH="你的库路径"
cd firstTriangle/build
cmake ..
cmake --build .
```

**Linux/Mac:**
```bash
export LIBS_PATH="你的库路径"
cd firstTriangle/build
cmake ..
cmake --build .
```

## 运行

编译完成后，在 `build` 目录下运行：
```bash
./firstTriangle      # Linux/Mac
.\firstTriangle.exe  # Windows
```

## 学习资源

- [LearnOpenGL CN](https://learnopengl-cn.github.io/)
- [LearnOpenGL (英文)](https://learnopengl.com/)

## 许可

本项目仅供学习使用。

