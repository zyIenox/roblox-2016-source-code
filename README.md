# Roblox Hitius Source Code
<small>*(Forked for personal use)*</small>

This repository contains fixed hitius source code that can be compiled.<br>
Acquired from web archive and brought to you in Github!<br>
   - **Original Link:**  [Go to the Original Web Archive Link](https://web.archive.org/web/20200907113312/https://git.hitius.com/root/roblox/-/archive/master/roblox-master.zip)

ui0ppk has an broken hitius source code, this is the original hitius version so its fixed.

## Sizes & Comparision
roblox-master-main.zip (Owned by ui0ppk, broken and missing some files.) = 781MB<br>
roblox-master-original.zip included Libraries (Owned by hitius, better and fixed one.) = 915MB

Libraries are excluded as a .7z file because of the size. [See the down below for downloading it](#requirements)

## Build

### Requirements
You will need the following to compile, for Windows:
- [Visual Studio 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=16)
   - You need these Components:
      1. Visual Studio 2015 Build Tools (v140_xp or v140)
      2. Desktop Development with C++ from Workloads
- [Visual Studio 2017](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15)
   - You need these Components:
     1. Windows XP Support for C++
     2. Visual C++ ATL for x86 and x64
     3. Visual C++ MFC for x86 and x64
- [7-Zip](https://www.7-zip.org/) (Optional)
- [Library.7z](https://mega.nz/file/eyQyWaiL) - Excluded Libraries
   - Encrpytion Key: `JyaWhnQ6MrvdF5h03ts_4ingrVQzBIcEV4NpU1tcUTY`

### Setting up Libraries

1. Create a folder named "Library" to the root
2. Unzip the Library.7z to the "Library" folder that you created and then continue reading the tutorial.

### Boost
1. Run `bootstrap.bat` in `Library/boost/`. Edit the paths in `build_boost.bat` to correspond to where you are keeping this repository, and run `build_boost.bat`
2. Congratulations! You've built boost.

### Qt
1. This is where the necessity of the Visual Studio 2015 build tools becomes apparent. You will need to open the VS2015 x86 Native Tools Command Prompt (search VS2015 in your Start Menu.)
2. Set your current directory to this repositorys Library/Qt folder.
3. Run the following command, substituting "${path}" for where you are keeping this repository.
```sh
configure -make nmake -platform win32-msvc2015 -prefix ${path}\Library\Qt -opensource -confirm-license -opengl desktop -nomake examples -nomake tests -webkit -xmlpatterns
```
4. Example command if I kept the repository in `D:\Roblox\Source`:
```sh
configure -make nmake -platform win32-msvc2015 -prefix D:\Roblox\Source\Library\Qt -opensource -confirm-license -opengl desktop -nomake examples -nomake tests -webkit -xmlpatterns
```
5. That will configure everything. Once it is finished, run `nmake`. If you get an error for `rc` not being recognized, add your SDK to PATH.
6. It should eventually stop and break somewhere, but by that time, you will have all the libraries you need.
7. Congratulations! You *partially* compiled Qt.

### Main Roblox projects
Simply open up Roblox.sln with **Visual Studio 2019** and build. Everything listed as able to compile will compile, unless you're doing something wrong.

## Libraries
Library names suffixed with an asterisk (\*) denote a library that is currently out of date.

- Boost v1.74.0
- libcurl v7.71.0
- zlib v1.12.11
- SDL v2.0.12
- VMProtect v2.1.3 \*
- cpp-netlib v0.13.0-final
- Mesa v7.8.1 \*
- xulrunner-sdk v1.9.0.11.en-US.win32.sdk \*
- glsl-optimizer \*
- hlsl2glsl \*
- cabsdk \*
- Windows/DirectX SDK
- w3c-libwww v5.4.2
- Qt 4.8.5 \*

## Extras
This is a complete and comprehensive list of all the major changes made to the original source code.

- [x] Added all the "Contrib" libraries (see above)
- [ ] Able to compile, and run successfully all projects
	- [x] App
	- [x] AppDraw
	- [x] Network
	- [x] RCCService
	- [x] Base
	- [x] boost.static
	- [x] boost.test
	- [x] GfxBase
	- [x] RbxG3D
	- [x] graphics3D
	- [x] RbxTestHooks
	- [ ] Base.UnitTest
	- [ ] App.UnitTest
	- [x] RobloxStudio
	- [x] Log
	- [x] WindowsClient
	- [ ] RobloxTest
	- [x] GfxCore
	- [x] GfxRender
	- [x] CSG
	- [x] App.BulletPhysics
	- [ ] CoreScriptConverter2
	- [ ] Microsoft.Xbox.GameChat
	- [ ] Microsoft.Xbox.Samples.NetworkMesh
	- [ ] XboxClient
	- [ ] Bootstrapper
	- [ ] BootstrapperClient
	- [x] RobloxProxy
	- [x] NPRobloxProxy
	- [ ] BootstrapperQTStudio
	- [ ] BootstrapperRCCService
	- [ ] RCCServiceArbiter
	- [x] RobloxModelAnalyzer
	- [ ] Extract RbxDebug source files from bin/obj files
	- [ ] MacClient
	- [ ] RobloxMac
	- [ ] Android
	- [ ] iOS
- [ ] Backported features
	- [ ] Studio dark theme
	- [ ] Constraints
	- [ ] Sound.PlaybackSpeed
	- [ ] ScreenGui.Enabled
	- [ ] ScreenGui.DisplayOrder
	- [ ] Atmosphere
	- [ ] Instance
		- [x] Wait
		- [x] Connect
		- [ ] GetPropertyChangedSignal
	- [ ] AnimationTrack.Looped
	- [ ] Color3uint8
	- [x] Sky
		- [x] SunAngularSize
		- [x] MoonAngularSize
		- [x] SunTextureId
		- [x] MoonTextureId
	- [x] Lighting
		- [x] ClockTime
	- [ ] Post Processing
		- [x] MSAA
			- [ ] AASamples
		- [ ] BloomEffect
		- [ ] BlurEffect
		- [ ] ColorCorrectionEffect
		- [ ] SunRaysEffect
		- [ ] Attempt a backport of the 2015 1x1 stud voxel shadow FIB prototype (demo [here in 2015,](https://www.youtube.com/watch?v=z5TmqDtpwSM) and [here in 2014](https://www.youtube.com/watch?v=Y9-KDzMasjg))
	- [ ] TextSize
	- [x] Easier to read debug stat GUIs
	- [ ] LayerCollector.ResetOnSpawn
	- [x] "Oof" sound in volume slider
	- [ ] Smooth camera scrolling
	- [ ] Color3
		- [x] Color3.fromRGB
		- [ ] Color3.fromHSV
		- [ ] Color3.toHSV
	- [ ] Instance:GetDescendants()
	- [ ] MeshPart
	- [ ] Terrain
		- [ ] WaterReflectance
		- [ ] MaterialColors
		- [ ] New 2020 materials
	- [ ] Sound effects
		- [ ] FlangeSoundEffect
		- [ ] SoundEffect
		- [ ] SoundGroup
		- [ ] PitchShiftSoundEffect
		- [ ] ChorusSoundEffect
		- [ ] CompressorSoundEffect
		- [ ] TremoloSoundEffect
		- [ ] ReverbSoundEffect
		- [ ] DistortionSoundEffect
		- [ ] EchoSoundEffect
		- [ ] EqualizerSoundEffect
	- [ ] ScreenGui.IgnoreGuiInset
	- [ ] TextBox
		- [ ] TextBox.CursorPosition
		- [ ] TextBox.SelectionStart
		- [ ] Home / End key compatibility with this
	- [ ] New Developer Console
	- [ ] Team
		- [ ] Player.Team
		- [ ] Team:GetPlayers()
		- [ ] Team.PlayerAdded
		- [ ] Team.PlayerRemoved
	- [ ] Particle visiblity
		- [ ] ForceField.Visible
		- [ ] Explosion.Visible
	- [ ] Decal.Color3
	- [ ] ClickDetector
		- [ ] ClickDetector.RightMouseClick
		- [ ] ClickDetector.CursorIcon
	- [ ] HttpService headers in HttpService:GetAsync and HttpService:PostAsync
	- [ ] Humanoid.FloorMaterial
	- [ ] Smooth camera scrolling
- [ ] New features
	- [x] WaterWave{Size|Speed} can be in the range of -FLT_MIN to FLT_MAX
	- [ ] TextBox text selection
	- [ ] Bring back SafeChat (Studio Settings -> Game Options -> ShowSafeChatButton)
	- [ ] `int64`
	- [ ] Unicode/UTF8
	- [ ] 64-bit support
	- [ ] Compile as VC++ 2019
	- [x] Uncap friction
	- [ ] Lua 5.3 (or, port over the Lua 5.3 utf8 library)
	- [ ] Unlock TextureTrail
	- [x] Uncap PlayerGui:SetTopbarTransparency
	- [ ] Mesh format version 3.00 support
	- [ ] Color3.toRGB
- [ ] Bug fixes
	- [ ] DirectX
		- [x] DirectX 9 [ text render bug ] [ fixed, apparently never existed in first place ]
		- [ ] DirectX 11 [ not initializing ]
	- [x] SDL Windows Key
	- [x] Keyboard Shortcuts
	- [x] Chat output being smaller upon minimize
