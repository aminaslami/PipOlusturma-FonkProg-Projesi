# PIP Oluşturma Projesi - 175541611 Mohammad Amin ASLAMI (Danışman: Dr. Öğr. Üyesi Yunus SANTUR)


## ÖNEMLİ: Pip sürümünün yükseltilmiş olduğundan emin olun
**Windows**
```
py -m pip install --upgrade pip
```

Linux/MAC OS
```
python3 -m pip install --upgrade pip
```

## Aşağıdaki yapıya sahip bir proje oluşturun
```
packaging_tutorial/
├── LICENSE
├── pyproject.toml
├── README.md
├── setup.cfg
├── src/
│   └── GetMode/
│       ├── __init__.py
│       └── Mode.py
└── tests/
touch LICENSE
touch pyproject.toml
touch setup.cfg
mkdir src/mypackage
touch src/mypackage/__init__.py
touch src/mypackage/main.py
mkdir tests
```

## pyproject.toml 

Bu dosya, pip ve build gibi araçlara projenizi nasıl oluşturacağınızı anlatır.

```
[build-system]
requires = [
    "setuptools>=42",
    "wheel"
]
build-backend = "setuptools.build_meta"
```
build-system.requires, paketinizi oluşturmak için gereken paketlerin bir listesini verir. Burada bir şey listelemek, onu kurulduktan sonra değil, yalnızca derleme sırasında kullanılabilir hale getirecektir.

build-system.build-backend, derlemeyi gerçekleştirmek için kullanılacak Python nesnesinin adıdır. Flit veya şiir gibi farklı bir yapı sistemi kullanacak olsaydınız, bunlar buraya gelirdi ve yapılandırma ayrıntıları aşağıda açıklanan setuptools yapılandırmasından tamamen farklı olurdu.

# Setup.cfg setup
setup.cfg kullanmak en iyi uygulamadır, ancak setup.py kullanarak dinamik bir kurulum dosyanız olabilir.

```
[metadata]
name = Amin_Get_Mode_Version3
version = 0.0.3
author = Amin
author_email = aminaslamiaf@gmail.com
description = You can get mode easily - Amin Aslami
long_description = file: README.md
long_description_content_type = text/markdown
url = https://github.com/pypa/sampleproject
project_urls =
    Bug Tracker = https://github.com/pypa/sampleproject/issues
classifiers =
    Programming Language :: Python :: 3
    License :: OSI Approved :: MIT License
    Operating System :: OS Independent

[options]
package_dir =
    = src
packages = find:
python_requires = >=3.6

[options.packages.find]
Nerede = src

```
# Yapının çalıştırılması
### Yapı aracınızın güncel olduğundan emin olun
Windows
```
py -m pip install --upgrade build
```
Linux/MAC OS
```
python3 -m pip install --upgrade build
```

### Yapıyı oluşturun
```
py -m build
```


### Referanslar
https://packaging.python.org/tutorials/packaging-projects/
