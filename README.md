![](https://github.com/wniemiec-task-java/checkpoint/blob/master/docs/img/logo/logo.jpg)

<h1 align='center'>Checkpoint</h1>
<p align='center'>A checkpoint is a class and method marker, and it is used when you want a piece of code, even if executed by several independent processes, to be executed only once.</p>
<p align="center">
	<a href="https://github.com/wniemiec-task-java/checkpoint/actions/workflows/windows.yml"><img src="https://github.com/wniemiec-task-java/checkpoint/actions/workflows/windows.yml/badge.svg" alt=""></a>
	<a href="https://github.com/wniemiec-task-java/checkpoint/actions/workflows/macos.yml"><img src="https://github.com/wniemiec-task-java/checkpoint/actions/workflows/macos.yml/badge.svg" alt=""></a>
	<a href="https://github.com/wniemiec-task-java/checkpoint/actions/workflows/ubuntu.yml"><img src="https://github.com/wniemiec-task-java/checkpoint/actions/workflows/ubuntu.yml/badge.svg" alt=""></a>
	<a href="https://codecov.io/gh/wniemiec-task-java/checkpoint"><img src="https://codecov.io/gh/wniemiec-task-java/checkpoint/branch/master/graph/badge.svg?token=R2SFS4SP86" alt="Coverage status"></a>
	<a href="http://java.oracle.com"><img src="https://img.shields.io/badge/java-11+-D0008F.svg" alt="Java compatibility"></a>
	<a href="https://mvnrepository.com/artifact/io.github.wniemiec-task-java/checkpoint"><img src="https://img.shields.io/maven-central/v/io.github.wniemiec-task-java/checkpoint" alt="Maven Central release"></a>
	<a href="https://github.com/wniemiec-task-java/checkpoint/blob/master/LICENSE"><img src="https://img.shields.io/github/license/wniemiec-task-java/checkpoint" alt="License"></a>
</p>
<hr />

## ❇ Introduction
If you need to know if a piece of code has already been executed by another process, then this is the perfect library for you. A checkpoint is a class and method marker, and it is used when you want a piece of code, even if executed by several independent processes, to be executed only once.

## ❓ How to use
1. Add one of the options below to the pom.xml file: 

#### Using Maven Central (recomended):
```
<dependency>
  <groupId>io.github.wniemiec-task-java</groupId>
  <artifactId>checkpoint</artifactId>
  <version>LATEST</version>
</dependency>
```

#### Using GitHub Packages:
```
<dependency>
  <groupId>wniemiec.task.java</groupId>
  <artifactId>checkpoint</artifactId>
  <version>LATEST</version>
</dependency>
```

2. Run
```
$ mvn install
```

3. Use it
```
[...]

import wniemiec.task.java.Checkpoint;

[...]

public class CheckpointExample {

[...]

Checkpoint checkpoint = new Checkpoint(tmpDir, "checkpoint-example");

System.out.println("Trying to access piece of code...");

if (checkpoint.isEnabled()) {
	System.out.println("Piece of code already executed");
}
else {
	System.out.println("Piece of code executed for the first time");
	checkpoint.enable();
}

System.out.println("...");

while (true) {
}

[...]
```

```
Process one

$ java CheckpointExample
$ Trying to access piece of code...
$ Piece of code executed for the first time
$ ...
```

```
Process two

$ java CheckpointExample
$ Trying to access piece of code...
$ Piece of code already executed
$ ...
```

## 📖 Documentation
|        Property        |Parameter type|Return type|Description|Default parameter value|
|----------------|-------------------------------|-----------------------------|--------|
|enable |`void`|`void`|Starts a new checkpoint| - |
|disable |`void`|`void`|Disables checkpoint| - |
|exists |`void`|`boolean`|Checks if a checkpoint was created.| - |
|isEnabled |`void`|`boolean`|Checks if the checkpoint is active.| - |
|delete | `void`|`void`|Checks if the checkpoint is active.| - |

## 🚩 Changelog
Details about each version are documented in the [releases section](https://github.com/williamniemiec/wniemiec-task-java/checkpoint/releases).

## 🤝 Contribute!
See the documentation on how you can contribute to the project [here](https://github.com/wniemiec-task-java/checkpoint/blob/master/CONTRIBUTING.md).

## 📁 Files

### /
|        Name        |Type|Description|
|----------------|-------------------------------|-----------------------------|
|dist |`Directory`|Released versions|
|docs |`Directory`|Documentation files|
|src     |`Directory`| Source files|
