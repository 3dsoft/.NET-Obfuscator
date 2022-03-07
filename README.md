<!-- Badges -->
![GitHub contributors](https://img.shields.io/github/contributors/NotPrab/.NET-Obfuscator?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/NotPrab/.NET-Obfuscator?style=for-the-badge)
![GitHub Repo stars](https://img.shields.io/github/stars/NotPrab/.NET-Obfuscator?style=for-the-badge)
![GitHub issues](https://img.shields.io/github/issues/NotPrab/.NET-Obfuscator?style=for-the-badge)
![GitHub](https://img.shields.io/github/license/NotPrab/.NET-Obfuscator?style=for-the-badge)


<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/NotPrab/.NET-Obfuscator">
    <img src="https://www.kitto.app/image/logo-microsoft-net.png" alt="Logo" width="238" height="238">
  </a>

  <h3 align="center">.NET Obfuscator</h3>

  <p align="center">
    💻 🎉  Awesome lists about all kinds of interesting .NET Obfuscator.
    <br />
    <a href="https://github.com/NotPrab/.NET-Obfuscator/discussions">Discussions</a>
    ·
    <a href="https://github.com/NotPrab/.NET-Obfuscator/issues">Report Bug</a>
    ·
    <a href="https://github.com/NotPrab/.NET-Obfuscator/pulls">Request Feature</a>
  </p>
</p>

<!-- ABOUT THE PROJECT -->
## 프로젝트 소개

인터넷에서 사용할 수 있는 훌륭한 .Net 난독화 프로그램이 많지만 제 요구에 정말 맞는것을 찾지 못해 이 목록을 만듭니다.

<!-- utilization EXAMPLES -->
## Utilization

Java 및 .NET과 같은 특정 언어는 쉽게 읽을 수 있는 소스 코드로 디컴파일할 수 있습니다. 코드 난독화는 디컴파일러로 애플리케이션 바이너리를 읽기 어렵게 만드는 프로세스입니다. 기업의 지적 재산을 보호하기 위한 중요한 도구입니다.

### 코드를 난독화하는 이유는 무엇입니까?

C++와 같은 컴파일된 언어는 바이트코드로 직접 변환됩니다. 작동 방식을 리버스 엔지니어링하는 유일한 방법은 어렵고 복잡한 프로세스인 디스어셈블러를 사용하는 것입니다. 불가능한 것은 아니지만 어셈블리 언어 스트림에서 높은 수준의 응용 프로그램 논리를 추론하는 것은 어렵습니다.

반면에 C# 및 Java와 같은 언어는 특정 운영 체제용으로 컴파일되지 않습니다. 오히려 .NET의 MSIL과 같은 중간 언어로 컴파일됩니다. 중개 언어는 어셈블리와 유사하지만 쉽게 소스 코드로 다시 변환할 수 있습니다. 즉, 비즈니스에서 배포하는 공용 DLL 또는 실행 파일이 있는 경우 실행 파일의 복사본이 있는 사람은 누구나 dotPeek과 같은 .NET 디컴파일러에서 이를 열고 소스 코드를 직접 읽고(및 복사할) 수 있습니다.

코드 난독화는 이 프로세스를 막을 수 없습니다. 모든 .NET DLL을 디컴파일러에 연결할 수 있습니다. 난독화는 여러 가지 트릭을 사용하여 소스 코드를 읽고 디버그하는 데 짜증나게 만듭니다.

이것의 가장 간단한 형태는 엔티티 이름 바꾸기입니다. 그들이 하는 일에 따라 변수, 메소드, 클래스 및 매개변수의 이름을 적절하게 지정하는 것이 일반적입니다. 그러나 그럴 필요는 없으며 기술적으로 일련의 소문자 L과 I 또는 중국어 유니코드 문자의 임의 조합으로 이름을 지정하는 것을 막을 수 있는 방법은 없습니다. 컴퓨터에는 문제가 없지만 사람은 완전히 읽을 수 없습니다.

```
IlIIIIlIIIllIIIllIIll
lIIIllIIllIlIIIIlIIIl
```

기본 obfuscator는 이 프로세스를 자동으로 처리하여 빌드에서 출력을 가져와 훨씬 더 읽기 어려운 것으로 변환합니다. 난독화되지 않은 코드에 비해 성능 저하가 없습니다 .

고급 난독화 도구는 더 나아가 소스 코드의 구조를 실제로 변경할 수 있습니다. 여기에는 제어 구조를 더 복잡하지만 의미상 동일한 구문으로 바꾸는 것이 포함됩니다. 그들은 또한 디컴파일러를 혼동시키는 것 외에는 아무 것도 하지 않는 더미 코드를 삽입할 수 있습니다. 이것의 효과는 소스를 스파게티 코드처럼 보이게 하여 읽기를 더 성가시게 만든다는 것입니다.

또 다른 일반적인 초점은 디컴파일러에서 문자열을 숨기는 것입니다. 관리되는 실행 파일에서 오류 메시지와 같은 문자열을 검색하여 코드 섹션을 찾을 수 있습니다. 문자열 난독화는 문자열을 인코딩된 메시지로 바꿉니다. 이 메시지는 런타임에 해독되므로 디컴파일러에서 문자열을 검색할 수 없습니다. 이것은 일반적으로 성능 저하와 함께 제공됩니다.

### 기타 옵션: 컴파일된 언어로 변환

한 프로그래밍 언어를 다른 프로그래밍 언어로 변환하는 것은 완전히 미친 아이디어가 아닙니다. Unity는 .NET 코드를 컴파일된 C++ 바이트코드로 변환하는 변환기인 IL2CPP를 사용합니다. 성능은 훨씬 뛰어나지만 불법 복제와 사기꾼이 만연한 환경에서 중요한 쉬운 크래킹으로부터 게임을 보호하는 데도 도움이 됩니다.

Microsoft에는 Ahead-Of-Time 컴파일을 사용하는 실험적인 .NET Core 런타임인 CoreRT 가 있지만 프로덕션용으로 사용할 준비가 되지 않았습니다.

### 난독화해야합니까?

소스 코드를 보호하려는 신뢰할 수 없는 환경에 코드를 배포하는 경우 거의 항상 최소한 기본 난독화기를 사용하여 함수, 메서드 및 속성의 이름을 변경하여 디컴파일에 더 많은 노력을 기울여야 합니다.

앱을 디컴파일할 수 있는 사람이 정말로 필요하지 않은 경우에는 더 방해가 되는 난독화 도구를 사용할 수 있지만 실제로 C++ 또는 녹.

<!-- ROADMAP -->
## Roadmap

제안된 기능(및 알려진 문제) 목록은 미해결 문제 를 참조하세요 .
https://github.com/NotPrab/.NET-Obfuscator/issues)


<!-- CONTRIBUTING -->
## Contributing

기여는 오픈 소스 커뮤니티를 배우고 영감을 주고 창조할 수 있는 놀라운 장소로 만드는 것입니다. 귀하의 기여에 크게 감사드립니다 .

1. 프로젝트를 포크
2. 분기 만들기 (`git checkout -b feature/AmazingFeature`)
3. 변경 사항 커밋 (`git commit -m 'Add some AmazingFeature'`)
4. 분기에 푸시 (`git push origin feature/AmazingFeature`)
5. 풀 리퀘스트 열기


<!-- LICENSE -->
## License

MIT 라이선스에 따라 배포됩니다. 자세한 내용은 LICENSE를 참조하십시오.
Distributed under the MIT License. See `LICENSE` for more information.

## References
코드 난독화란 무엇이며 사용해야 합니까? 앤서니 헤딩스
[What is Code Obfuscation, and Should you use it?](https://www.cloudsavvyit.com/6923/what-is-code-obfuscation-and-should-you-use-it/) by Anthony Heddings


<!-- Lists -->
## Lists of .NET Obfuscator

<!-- A -->
## A =>
### Agile
* [Agile](https://secureteam.net/acode-features-detailed)- .NET 앱을 위한 강력한 코드 보호, 난독화 및 라이선스 솔루션

### Aldaray Rummage Obfuscator
* [Aldaray Rummage Obfuscator](https://www.aldaray.com/) - 코드를 매듭으로 묶고 해커를 울게 만드십시오.
### AppFuscator
* [AppFuscator](https://appfuscator.com/) - 인텔리전스 알고리즘은 애플리케이션에 강력한 보호 기능을 제공합니다!
### ArmDot
* [ArmDot](https://www.armdot.com/) - 직렬 키 및 파일 임베딩을 지원하는 C# 및 .Net용 보호, 소프트웨어 라이선스 도구 및 난독화 도구
### Arya
* [Arya](https://github.com/HarmJ0y/Arya) - Arya는 .NET 바이너리를 위한 간단한 난독화 도구입니다
### AsStrongAsFuck
* [AsStrongAsFuck](https://github.com/Charterino/AsStrongAsFuck) - .NET 어셈블리용 콘솔 난독화 도구입니다.

------------------
<!-- B -->
## B =>
### Babel
* [Babel](https://www.babelfor.net/) - 리버스 엔지니어링으로부터 소프트웨어를 보호하여 코드의 지적 재산을 보호합니다.
### Beds Protector

* [Beds Protector](https://github.com/BedTheGod/ConfuserEx-Mod-By-Bed) - 침대 수호자 | 현재 최고의 무료 난독화(ConfuserEx Mod)
### BitHelmet

* [BitHelmet](https://bithelmet.software.informer.com/) - BitHelmet obfuscator는 .NET Portable Executables를 보호합니다.
### BoxedApp

* [BoxedApp](https://www.boxedapp.com/) - ActiveX, Flash 및 .Net 런타임 가져오기 및 가상화 • 개발자를 위한 풍부한 SDK • 맞춤형 패커 생성 • 32비트 및 64비트 애플리케이션 모두 지원 • 가상 파일 시스템 및 레지스트리
------------------
<!-- C -->
## C =>
### ConfuserEx

* [ConfuserEx](https://github.com/yck1509/ConfuserEx) - An open-source, free protector for .NET applications.
### ConfuserEx 2

* [ConfuserEx 2](https://github.com/mkaring/ConfuserEx) - Updated ConfuserEx (by mkaring), an open-source, free obfuscator for .NET applications.
### Crypto

* [Crypto](https://www.ssware.com/cryptoobfuscator/obfuscator-net.htm) - Powerful Obfuscation & Code Protection For .Net That Actually Works!
### Cyphor

* [Cyphor](https://cyphor.net/details) - Cyphor is more than just an obfuscator. Cyphor is the best, fastest, and most reliable obfuscation protection tool to work with.
### cil-examining

* [cil-examining](https://github.com/mira-ta/cil-examining) - A .NET Framework (.NET Core in the future) obfuscator. Owner is currently out sick thus working on project is stopped.
### Cheap Obfuscator

* [Cheap Obfuscator](https://github.com/Polymeth/cheap-obfuscator) - a pretty bad obfuscator made to learn
### Confuser1337

* [Confuser1337](https://github.com/ama6nen/Confuser1337) - bad 2016 code, i dont recommend anyone uses it
------------------
<!-- D -->
## D =>
### dotNetObfuscator

* [dotNetObfuscator](https://github.com/baskfx/dotNetObfuscator) - Обфускатор строки для C#
### DarkFuscator

* [DarkFuscator](https://github.com/isigov/.NET-Obfuscator) - Code obfuscator for .NET framework programs. Outdated in 2016, but was very functional in 2010/2011.Uses the Mono.Cecil library for interacting with .NET assemblies. 
### DarksProtector

* [DarksProtector](https://github.com/BillytheButcher/DarksProtector) - DarksProtector 2.0 | ConfuserEx Modded 
### DeepSea

* [DeepSea](https://deepsea-obfuscator.soft112.com/) - DeepSea Obfuscator makes obfuscation of your .NET assemblies an intuitive and integrated part of your product development.
### Demeanor

* [Demeanor](http://www.wiseowl.com/products/products.aspx) - Demeanor for.NET protects your intellectual property by making it extremely difficult to reverse engineer your .NET applications.
### Denvelope

* [Denvelope](https://github.com/TWVyY3VyaW8K/Denvelope) - NET Obfuscator
### DNGuard HVM

* [DNGuard HVM](http://www.dnguard.net/index.php) - Advanced .NET Code Protection and Obfuscation Technology
### Dotfuscator

* [Dotfuscator](https://www.preemptive.com/products/dotfuscator/overview) - Dotfucator's .NET obfuscation and runtime checks have protected thousands of apps for over a decade.
### DotNetGuard

* [DotNetGuard](https://github.com/Modify24x7/DotNetGuard) - .Net Protector ( ConfuserEx Mod )
### DotNetPatcher

* [DotNetPatcher](https://github.com/mwsrc/DotNetObfuscator) - DotNetObfuscator
### DotNetSafer

* [DotNetSafer](https://dotnetsafer.com/) - Increase the security of your software, reduce costs and save time with the tools that dotnetsafer offers you to protect your intellectual property and guarantee the integrity of your .NET and .NET Core applications.
### Dotpack

* [Dotpack](https://github.com/daeken/Dotpack/) - Extreme (TM) binary packer for .NET 
### DCNETProtector

* [DCNETProtector](https://github.com/dcsoft-yyf/DCNETProtector) - An open source tool to encrypt .NET assembly file, help people protect theirs copyright. It has a command line interface and some specific features. It claims to have only 6000 lines of code.
------------------
<!-- E -->
## E =>

### Eazfuscator

* [Eazfuscator](https://www.gapotchenko.com/eazfuscator.net) - Eazfuscator.NET is the obfuscator for .NET platform. 
### Enigma Protector

* [Enigma Protector](https://enigmaprotector.com/en/about.html) - A professional system for licensing and protecting
executable files for Windows.
### ElecKey

* [ElecKey](https://www.sciensoft.com/) - ElecKey is a suite of software and tools that provide a complete solution for software security, copy protection, and license management. It allows you to protect your software against piracy, tampering, and reverse-engineering, as well as gain full control over secure software distribution and licenses.
------------------
<!-- G -->
## G =>

### Guardship-.NET-Protector

* [Guardship-.NET-Protector](https://github.com/Rustemsoft/Guardship-.NET-Protector) - Guardship .NET Protector is a development software that helps to protect the executable file of .NET application by making its code unreadable for MSIL disassemblers.
### Goldfuscator

* [Goldfuscator](https://github.com/AnErrupTion/Goldfuscator) - A fork of the original SimpleObfuscator project, made for training. 
------------------
<!-- H -->
## H =>

### Habib Extreme Protector

* [Habib Extreme Protector](https://discord.gg/rQ4P6ZV) - A Strong .NET Obfuscator & Protector
------------------
<!-- I -->
## I =>
### ILProtector

* [ILProtector](http://www.vgrsoft.net/Products/ILProtector) - ILProtector is a protector for .NET applications. ILProtector is designed to protect intellectual property of the software.

### IntelliLock

* [IntelliLock](https://www.eziriz.com/intellilock.htm) - IntelliLock is an advanced 100% managed solution for licensing controls and applications. While .NET Reactor offers a licensing system based on native code protection, IntelliLock opts a 100% managed way to apply licensing and protection features. This way single files can be produced without the need of additional files. 
### IntelliProtector

* [IntelliProtector](https://intelliprotector.com/Products/Net-Obfuscator/Features) - IntelliProtector .Net Obfuscator is excellent Free tool for your IntelliProtector .Net projects.

------------------
<!-- K -->
## K =>

### Krawk Protector

* [Krawk Protector](https://github.com/cristlxrd/Krawk-Protector) - .NET Obfuscator and Protector 
### KoiVM

* [KoiVM](https://github.com/Loksie/KoiVM-Virtualization) - Virtualization made for .NET using ConfuserEX 
------------------
<!-- L -->
## L =>

### lookatme

* [lookatme](https://github.com/pjc0247/lookatme) - NET Obfuscator for Studying purpose.
### Lime-Crypter

* [Lime-Crypter](https://github.com/NYAN-x-CAT/Lime-Crypter) - An obfuscation tool for .Net + Native files.
### LoGic.NET

* [LoGic.NET](https://github.com/AnErrupTion/LoGiC.NET) - A more advanced free and open .NET obfuscator using dnlib.
------------------
<!-- M -->
## M =>

### MancoSoftware

* [MancoSoftware](http://www.mancosoftware.com/) - Manco .NET Licensing System is the powerful licensing and copy protection software for .NET Windows Forms, WPF, WCF, WWF and ASP.NET applications, controls and components.
### MdCrypt

* [MdCrypt](https://github.com/wwh1004/Mdcrypt) - [WIP] A next-generation protector for .NET applications (.NET Framework, .NET Core, and more) 
### MemeVM

* [MemeVM](https://github.com/TobitoFatitoNulled/MemeVM) - A small virtualizer for .NET which works together with ConfuserEx 

### MindLated

* [MindLated](https://github.com/Sato-Isolated/MindLated) -  .net obfuscator using dnlib  
### ModPhuserEx

* [ModPhuserEx](https://github.com/0xFireball/ModPhuserEx) - A .NET protector supporting .NET Core forked from the discontinued ConfuserEx
### MPRESS

* [MPRESS](http://www.matcode.com/) - Free high-performance executable packer for PE32/PE32+/.NET executable formats!
------------------
<!-- N -->
## N =>

### netshrink

* [netshrink](https://www.pelock.com/products/netshrink) - netshrink is an exe packer aka executable compressor, application password protector and virtual DLL binder for Windows & Linux .NET applications.
### Neo ConfuserEx

* [Neo ConfuserEx](https://github.com/XenocodeRCE/neo-ConfuserEx) - Updated ConfuserEX, an open-source, free obfuscator for .NET applications
### NetFuscate

* [NetFuscate](http://netfuscate.com/) - NETFuscate is a .NET obfuscator and a .NET code protection tool that offers protection against reverse engineering of your code.
### NetShields

* [NetShields](https://discord.gg/baVPenN) - A really strong & recommended for .NET Obfuscator
### NETGuard

* [NETGuard](https://netguard.io/) - NETGuard.IO will decompose your file, encrypt your strings, data, resources, methods, will perform numerous runtime-based verifications to ensure a fully-shielded security for 
your file. The list of feature can be founded on our official documentation page. 
### NET Reactor

* [NET Reactor](https://www.eziriz.com/) - NET Reactor is a powerful .NET code protection and software licensing system which completely stops any decompiling.
### NETZ Compressor

* [NETZ Compressor](https://github.com/madebits/msnet-netz-compressor) - 2004 .NETZ compresses Microsoft .NET executables 
### NET-Obfuscator

* [NET-Obfuscator](https://github.com/NightBaron/.NET-Obfuscator) - Simple .net obfuscator using Mono Cecil
### Noisette

* [Noisette](https://github.com/XenocodeRCE/Noisette-Obfuscator) - An Obfuscator for .NET assembly 

------------------
<!-- O -->
## O =>

### obfuscatus

* [obfuscatus](https://github.com/stschake/obfuscatus) - a .NET obfuscator based on mono cecil
### ObfuscationAttributes

* [ObfuscationAttributes](https://github.com/obfuscators-2019/ObfuscationAttributes) - Add watermarks of obfuscators, makes de4dot think your file is obfuscated. bad 2016 code, i dont recommend anyone uses it
### Obfuscord

* [Obfuscord](https://github.com/TobitoFatitoNulled/Obfuscord) - Obfuscates A file Through Discord as a Bot using Discord.Net Api
### Obfuscar

* [Obfuscar](https://github.com/obfuscar/obfuscar) - Open source obfuscation tool for .NET assemblies
### Obfuscator.NET 2009

* [Obfuscator.NET 2009](http://www.macrobject.com/en/obfuscator/index.htm) - Protect your .NET assembly
### OctopusObfuscator

* [OctopusObfuscator](https://github.com/Alxs009/OctopusObfuscator) - Basic obfuscator for .NET
### Orange Heap obfuscator

* [Orange Heap obfuscator](http://orangeheap.blogspot.com/) - free and efficient way to protect your .NET software
------------------
<!-- P -->
## P =>

### pshield

* [pshield](https://github.com/developervariety/pshield) - Plugin-based obfuscator
### Panda-Obfuscator

* [Panda-Obfuscator](https://github.com/barotyson/Panda-Obfuscator) - PandaObfuscator an simple Obfuscator, free, OpenSource for .Net Applications 
### PAOfuscator

* [PAOfuscator](https://github.com/Schaboom/PAOfuscator) - Obfuscator für Paradise.de
### PC Guard

* [PC Guard](http://www.sofpro.com/pc-guard) - Professional software protection and licensing system for .NET framework (x86, AnyCpu, x64) and Windows 32bit and 64 bit applications.
### PEunion

* [PEunion](https://github.com/bytecode77/pe-union) - PEunion (Binder, Crypter & Downloader)
### Phoenix Protector

* [Phoenix Protector](https://ntcore.com/?page_id=384) - .NET Obfuscator & Protector
### PV Logiciels dotNet Protector

* [PV Logiciels dotNet Protector](http://www.pvlog.com/) - PV Logiciels dotNet Protector is a powerful .NET code protection system that prevents your assemblies from being decompiled.
------------------
<!-- R -->
## R =>

### Rzy Protector

* [Rzy Protector](https://github.com/Riziebtw/RzyProtector) - Rzy Protector | A public confuserex modded
------------------
<!-- S -->
## S =>

### Semantic Designs

* [Semantic Designs](http://www.semdesigns.com/products/obfuscators/csharpobfuscator.html) - The C# Obfuscator tool scrambles C# source code to make it very difficult to understand or reverse-engineer 
### Self-Morphing C# Binary

* [Self-Morphing C# Binary](https://github.com/bytecode77/self-morphing-csharp-binary) - C# binary that mutates its own code, encrypts and obfuscates itself on runtime
### SharpObfuscator

* [SharpObfuscator](https://archive.codeplex.com/?p=sharpobfuscator) - It is a Software Protection tool, designed to help .NET developers efficiently protect their software. It will obfuscate and protect your .NET code, optimize your .NET assembly for better deployment, minimize distribution size, increase performance & add powerful post-deployment debugging capabilities.
### Skater .NET Obfuscator

* [Skater .NET Obfuscator](http://rustemsoft.com/obfuscator.aspx) - Rustemsoft proposes Skater .NET Obfuscator, an obfuscation tool for .NET code protection. It implements all known software protection techniques and obfuscation algorithms.
### SkiDzEX

* [SkiDzEX](https://github.com/NotPrab/SkiDzEX) - A modded version of ConfuserEx | SkiDzEx
### SmartAssembly

* [SmartAssembly](https://www.red-gate.com/products/dotnet-development/smartassembly/) - Protect your .NET code and IP with SmartAssembly
### String Encrypt

* [String Encrypt](https://www.pelock.com/products/string-encrypt) - Encrypt strings in source code & files using randomly generated algorithms, and generate the corresponding unique decryption code for any supported programming language.
### StrongVM

* [StrongVM](https://github.com/Modify24x7/StrongVM) - StrongVM is a virtualizing protector for .NET applications.
### SourceCodeObfuscator

* [SourceCodeObfuscator](https://github.com/0x000N3X4N/SourceCodeObfuscator) - C# source code obfuscator
### SpecterObfuscator

* [SpecterObfuscator](https://github.com/xXeptioN/SpecterObfuscator/tree/master/Obfuscator) - This Application will obfuscate your .NET Assembly
### Spices

* [Spices](https://www.9rays.net/Category/55-spicesnet-obfuscator.aspx) - Spices.Net Obfuscator is a .Net code obfuscation, protection and optimization tool that offers the wide range of technologies to completely protect your .Net code and secure your data.
------------------
<!-- T -->
## T =>

### Themida

* [Themida](https://www.oreans.com/Themida.php) - Advanced Windows software protection system
### Trinity-ConfuserEx-Mod

* [Trinity-ConfuserEx-Mod](https://github.com/TrinityNET/Trinity-ConfuserEx-Mod) - A modded ConfuserEx created by Mighty, Bed and Centos. 
------------------
<!-- U -->
## U =>

### Unikod

* [Unikod](https://github.com/SDSkyKlouD/Unikod) - Text styling & obfuscation library for C# 
------------------
<!-- V -->
## V =>

### vot4cs

* [vot4cs](https://github.com/tum-i22/vot4cs) - A Virtualization Obfuscation Tool for C# program
### VaporObfusactor

* [VaporObfusactor](https://github.com/call-042PE/VaporObfuscator) - VaporObfuscator is an obfuscator for .net made with dnlib 
### VMProtect 3.4

* [VMProtect 3.4](https://vmpsoft.com/20190803/vmprotect-3-4/) - VMProtect protects code by executing it on a virtual machine with non-standard architecture that makes it extremely difficult to analyze and crack the software. Besides that, VMProtect generates and verifies serial numbers, limits free upgrades and much more.
------------------
<!-- Y -->
## Y =>

### Yano

* [Yano](https://yano.informer.com/) - Yano is an advanced obfuscator for Microsoft .NET applications 
------------------
<!-- Z -->
## Z =>

### Z00bfuscator

* [Z00bfuscator](https://github.com/Dentrax/Z00bfuscator) - Z00bfuscator is the simple, open-source, cross-platform obfuscator for .NET Assemblies built on .NET Core 

