<!-- {% raw %} -->
# Makefile: build-files-f26-020

% git status

```console
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit (use -u to show untracked files)
```

Changed files:

```console
Makefile
```

Source: Implementation

```Make
# Build for srccomplexity

.PHONY:all
all : srccomplexity srcMLXPathCountTest

srccomplexity : srcComplexity.o srcMLXPathCount.o
	g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity

srcComplexity.o : srcComplexity.cpp srcMLXPathCount.hpp
	g++ -I/usr/include/libxml2 -c srcComplexity.cpp

srcMLXPathCount.o : srcMLXPathCount.cpp srcMLXPathCount.hpp
	g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp

srcMLXPathCountTest : srcMLXPathCountTest.o srcMLXPathCount.o
	g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

srcMLXPathCountTest.o : srcMLXPathCountTest.cpp srcMLXPathCount.hpp
	g++ -c srcMLXPathCountTest.cpp

run : srccomplexity
	./srccomplexity srcMLXPathCount.cpp.xml

clean :
	@rm -f srccomplexity srcMLXPathCountTest srcComplexity.o srcMLXPathCount.o srcMLXPathCountTest.o

```

## Comparison

Closest match: Section 020

% diff Makefile

```diff
```

% diff commit messages

```diff
```

## Steps

### Step 1: Add header comment to the Makefile ✓

Makefile ✓

Build ✓

```console
$ make
make: *** No targets.  Stop.
(exit status 2)

# files created:
```

### Step 2: Add srcComplexity.cpp to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcComplexity.o
g++ -I/usr/include/libxml2 -c srcComplexity.cpp

# files created:
srcComplexity.o
```

### Step 3: Add srcMLXPathCount.cpp to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcMLXPathCount.o
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp

# files created:
srcMLXPathCount.o
```

### Step 4: Add executable srccomplexity to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srccomplexity
g++ -I/usr/include/libxml2 -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
```

### Step 5: Add srcMLXPathCountTest.cpp to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcMLXPathCountTest.o
g++ -c srcMLXPathCountTest.cpp

# files created:
srcMLXPathCountTest.o
```

### Step 6: Add executable srcMLXPathCountTest to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcMLXPathCountTest
g++ -c srcMLXPathCountTest.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

# files created:
srcMLXPathCount.o
srcMLXPathCountTest
srcMLXPathCountTest.o
```

### Step 7: Add target all to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make all
g++ -I/usr/include/libxml2 -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
srcMLXPathCountTest
srcMLXPathCountTest.o
```

### Step 8: Add PHONY to the target all ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make
g++ -I/usr/include/libxml2 -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
srcMLXPathCountTest
srcMLXPathCountTest.o
```

### Step 9: Add target clean to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make
g++ -I/usr/include/libxml2 -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest
$ make clean

# files created:
```

### Step 10: Add target run to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make run
g++ -I/usr/include/libxml2 -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
./srccomplexity srcMLXPathCount.cpp.xml
7

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
```


## Make

% make

```console
g++ -I/usr/include/libxml2 -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest
```

```console
total 92
-rw-rw-r-- 1 root root   818 Oct  6 16:16 Makefile
-rw-rw-r-- 1 root root   293 Oct  6 16:16 README.md
-rwxr-xr-x 1 root root 72616 Oct  7 15:47 srccomplexity
-rw-rw-r-- 1 root root   280 Oct  6 16:16 srcComplexity.1.md
-rw-rw-r-- 1 root root  1245 Oct  6 16:16 srcComplexity.cpp
-rw-r--r-- 1 root root  7064 Oct  7 15:47 srcComplexity.o
-rw-rw-r-- 1 root root  2086 Oct  6 16:16 srcMLXPathCount.cpp
-rw-rw-r-- 1 root root  8379 Oct  6 16:16 srcMLXPathCount.cpp.xml
-rw-rw-r-- 1 root root   664 Oct  6 16:16 srcMLXPathCount.hpp
-rw-r--r-- 1 root root  3528 Oct  7 15:47 srcMLXPathCount.o
-rwxr-xr-x 1 root root 71080 Oct  7 15:47 srcMLXPathCountTest
-rw-rw-r-- 1 root root   130 Oct  6 16:16 srcMLXPathCountTest.cpp
-rw-r--r-- 1 root root  1280 Oct  7 15:47 srcMLXPathCountTest.o
```

## Commit Messages

```console
7519746 Add target run to the build
f2d6e50 Add target clean to the build
c55da9f Add PHONY to the target all
4d263c7 Add target all to the build
8bdd80f Add executable srcMLXPathCountTest to the build
400d6dd Add srcMLXPathCountTest.cpp to the build
c2e355c Add executable srccomplexity to the build
916bd28 Add srcMLXPathCount.cpp to the build
5de2117 Add srcComplexity.cpp to the build
60b6328 Add header comment to the Makefile
6643896 Initial commit
```


<!-- {% endraw %} -->
