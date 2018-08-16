
# Windows

## Tools

[Firefox](https://www.mozilla.org/en-US/firefox/new)  
[Chrome](https://www.google.com/chrome)  
[Notepad++](https://notepad-plus-plus.org)  
[Visual Studio Code](https://code.visualstudio.com)  
[Visual Studio 2017 Community Edition](https://visualstudio.microsoft.com)  
[Git](https://git-scm.com)  
[CMake](https://cmake.org)  
[Malwarebytes](https://www.malwarebytes.com)  
[Sysinternals](https://docs.microsoft.com/en-us/sysinternals)  
[Acrobat Reader](https://get.adobe.com/reader)  
[7-zip](https://www.7-zip.org)  
[Cppcheck](http://cppcheck.sourceforge.net/)
[Cppcheck Visual Studio Plugin](https://github.com/VioletGiraffe/cppcheck-vs-addin)
[Clang for Windows](https://clang.llvm.org/)	

### Notepad++
		
	Settings > Style Configurator > Select theme: Zenburn
	Settings > Preferences > Backup > Remeber current session for next launch: no

### Visual Studio Code

[How to disable telemetry reporting](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)
	
	File > Preferences > Settings
		"telemetry.enableTelemetry": false
		
	Extensions
		CMake Tools (vector-of-bool)
		CMake (twxs)
		C/C++ (Microsoft)
		
### Visual Studio 2017 Community Edition

	Workload: Desktop development with C++

	Tools > Extensions and Updates... > Online > Visual Studio Marketplace
		Clang Power Tools
		ClangFormat

	Project Settings
		C/C++
			General
				Warning Level: Level4 (/W4)
			Precompiled Headers
				Precompiler Header: Not Using Precompiled Headers
			Language
				Conformance mode: Yes (/permissive-)
			C++ Language Standard
				ISO C++ Latest Draft Standard (/std:c++latest)
	
### Clang

	Settings (Toolbar) > Clang Power Tools > Tidy
		Use checks from: .clang.tidy config file

	.clang-tidy	
		Checks: '*'
		
### Cppcheck

	Tools > Cppcheck Settings
		Enable incolclusive checks
		Additonal arguments: --enable=all
		
### Sysinternals
		
	Process Explorer
	Options > VirusTotal.com > Check VirusTotal.com

### Git

	git config --global user.email "john.doe@gmail.com"
	git config --global user.name "John Doe"

### 7-zip

	Set file associations
	
## Other 

[github](https://github.com)