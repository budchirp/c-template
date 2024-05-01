<div align="center">
  <h1>c-template</h1>
</div>

<p align="center">
  <img alt="Stargazers" src="https://img.shields.io/github/stars/budchirp/c-template?style=for-the-badge&colorA=0b1221&colorB=ff8e8e" />
  <img alt="Last commit" src="https://img.shields.io/github/last-commit/budchirp/c-template?style=for-the-badge&colorA=0b1221&colorB=BDB0E4" />
  <img alt="Issues" src="https://img.shields.io/github/issues/budchirp/c-template?style=for-the-badge&colorA=0b1221&colorB=FBC19D" />
</p>


## 💾 Installation

### Requirements

1. C compiler
2. CMake

### How to install?

1. Clone the repo

```sh
git clone https://github.com/budchirp/c-template && cd c-template
```

2. Change the `EXEC_NAME` variable and project name on `CMakeLists.txt`

3. Compile the code

```sh
mkdir -p build && cd build
cmake ../ && make -j$(nproc)
```

> NOTE: If you're using fish, remove the `$` sign.

4. Have fun!
