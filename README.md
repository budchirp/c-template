<h1 align="center">c-template</h1>
<h2 align="center">C template for starting your projects faster</h2>

<p align="center">
  <img alt="Stargazers" src="https://img.shields.io/github/stars/budchirp/c-template?style=for-the-badge&colorA=0b1221&colorB=ff8e8e" />
  <img alt="Last commit" src="https://img.shields.io/github/last-commit/budchirp/c-template?style=for-the-badge&colorA=0b1221&colorB=BDB0E4" />
  <img alt="Issues" src="https://img.shields.io/github/issues/budchirp/c-template?style=for-the-badge&colorA=0b1221&colorB=FBC19D" />
</p>


## 💾

### Requirements

1. C compiler
2. CMake & Make

### How to start?

1. Clone the repo

```sh
git clone https://github.com/budchirp/c-template && cd c-template
```

2. Change project name in `CMakeLists.txt`

3. Compile the code

```sh
mkdir build && cd build
cmake .. && make -j$(nproc)
```

> NOTE: If you're using fish, remove the `$` sign.

4. Have fun!

```sh
./PROJECT_NAME
```
