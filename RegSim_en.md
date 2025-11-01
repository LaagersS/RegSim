# RegSim on macOS (ARM/Intel)

## Step 1: Check for Java

```bash
java -version
```

If Java is not installed, install it:

```bash
brew install --cask temurin
```

## Step 2: Prepare a folder for RegSim

Create a folder where you want to store RegSim:

```bash
mkdir -p YOUR_FOLDER_FOR_REGSIM
```

Place `regsim.jar` there (download from [https://www2.fiit.stuba.sk/~kristofik/other_en.html](https://www2.fiit.stuba.sk/~kristofik/other_en.html)).

Check that the file is in place:

```bash
ls -la YOUR_FOLDER_FOR_REGSIM
```

## Step 3: Download JavaFX SDK

Go to the folder with RegSim:

```bash
cd YOUR_FOLDER_FOR_REGSIM
```

**For ARM Mac (M1/M2/M3):**

```bash
curl -L -O https://download2.gluonhq.com/openjfx/21.0.1/openjfx-21.0.1_osx-aarch64_bin-sdk.zip
unzip openjfx-21.0.1_osx-aarch64_bin-sdk.zip
```

**For Intel Mac:**

```bash
curl -L -O https://download2.gluonhq.com/openjfx/21.0.1/openjfx-21.0.1_osx-x64_bin-sdk.zip
unzip openjfx-21.0.1_osx-x64_bin-sdk.zip
```

**Not sure which Mac you have?** Run:

```bash
uname -m
```

* `arm64` = ARM (M-series)
* `x86_64` = Intel

## Step 4: Run RegSim

```bash
cd YOUR_FOLDER_FOR_REGSIM
java --module-path ./javafx-sdk-21.0.1/lib --add-modules javafx.controls,javafx.fxml,javafx.graphics,javafx.swing -jar regsim.jar
```
