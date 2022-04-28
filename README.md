# Code Sight without Coverity Server
This is a simple example to show how to setup Synopsys Code Sight in VS Code without a Coverity Connect server.

## Prerequisites:
1.	Install Coverity Analysis(!) locally (e.g. `c:\usr\Coverity\cov-analysis-win64-2021.12.1`)
2.	Create a file `C:\Users\gunnar\AppData\Roaming\Coverity\coverity.conf`. Use [coverity.conf](/AppData/Roaming/Coverity/coverity.conf) in this repo and edit. 
3.	Install Code Sight plugin VS Code. Don't configure anything yet; just install it and close VS Code.

> :warning: In step 2, use the [coverity.conf](/AppData/Roaming/Coverity/coverity.conf) in the `AppData` subdirectory, not the one in the repository root.

## Using:
4.	Start a "Developer Command Prompt for VS 2019".
5.	Change into the project directory.
6.	Check if `msbuild hello-windows.sln` works.
7.	Start VS Code from there (type `code .`)
8.	Click on the Synopsys "S" on the left to activate the Code Sight plugin. It should say it found Coverity and will then download the Rapid Scan Static and Rapid Scan SCA engines (both <100MB, so should just take a couple of minutes).
9.	Go back to the VS Code File Explorer and open file hello-windows.cpp. In the status bar, you should see a message that Synopsys is scanning the file. Wait. It takes several minutes the first time. When it's done, you will see a "Dereferencing null pointer" defect in the source code and in the Code Sight view.

This should give you an idea how it works and you can play a bit. 
