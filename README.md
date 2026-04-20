# Rounds With Friends
 
A [ROUNDS](https://landfall.se/rounds) mod to extend the game's multiplayer capabilities, built for [BepInEx](https://github.com/BepInEx/BepInEx).

## Current Features

The mod supports up to 16 players in local and private online lobbies.

### Team Deathmatch

The game mode you are used to, except now it supports up to 16 players in various team compositions.

### Deathmatch / Free for all

Deathmatch follows the heart of the original team deathmatch game mode, but now it's just you against everyone else.

### Continue or rematch

After the game ends, you can choose to play a little longer, or to start a new game.

## Changelog

See [CHANGELOG.md](https://github.com/olavim/RoundsWithFriends/blob/main/CHANGELOG.md) for version changes.

## Dependencies

- [BepInEx](https://docs.bepinex.dev/master/articles/index.html) plugin framework
- [UnboundLib](https://github.com/Rounds-Modding/UnboundLib) version **>=2.11.0**

## Manual Installation

#### 0. Locate your ROUNDS install directory.

This directory is usually located at `C:\Program Files (x86)\Steam\steamapps\common\ROUNDS` or similar.

#### 1. Install **BepInEx**.

See [BepInEx installation](https://docs.bepinex.dev/master/articles/user_guide/installation/index.html) for details.

You can download the latest release directly from [BepInEx/releases](https://github.com/BepInEx/BepInEx/releases). Choose the correct version for your platform and extract the downloaded zip file to your ROUNDS installation directory in its entirety.

**Run the game once to generate BepInEx folder structure and configuration files.**

#### 2. Download **UnboundLib**.

Download the [latest release](https://github.com/Rounds-Modding/UnboundLib/releases/latest) of **[UnboundLib](https://github.com/Rounds-Modding/UnboundLib)** and extract the downloaded dll files to `ROUNDS/BepInEx/plugins`.

#### 3. Download **RoundsWithFriends**.

Download the [latest release](https://github.com/olavim/RoundsWithFriends/releases/latest) of **Rounds With Friends** and extract the downloaded zip file to the install directory of ROUNDS.

## Compile Instructions

> **Note:** Compiling requires the ROUNDS game to be installed, as the build references several managed DLLs from the game directory.

### Prerequisites (all platforms)

- [.NET SDK](https://dotnet.microsoft.com/download) (6.0 or later)
- [Git](https://git-scm.com/)
- ROUNDS installed via Steam

### Windows

1. **Install the .NET SDK** from [dotnet.microsoft.com](https://dotnet.microsoft.com/download).

2. **Clone the repository:**
   ```bat
   git clone https://github.com/dandol328/RoundsWithFriendsNew.git
   cd RoundsWithFriendsNew
   ```

3. **Set the ROUNDS install path** (if it differs from the default `C:\Program Files (x86)\Steam\steamapps\common\ROUNDS`):

   Create or edit `RoundsWithFriends/RoundsWithFriends.csproj.user` with the following content, replacing the path as needed:
   ```xml
   <Project>
     <PropertyGroup>
       <RoundsFolder>C:\Program Files (x86)\Steam\steamapps\common\ROUNDS</RoundsFolder>
     </PropertyGroup>
   </Project>
   ```

4. **Build the project:**
   ```bat
   dotnet build RoundsWithFriends.sln --configuration Release
   ```
   The compiled `RoundsWithFriends.dll` will be placed in `RoundsWithFriends\bin\Release\`.

   The post-build step will automatically run `publish.ps1` to package and copy the files to your ROUNDS install directory.

### Debian/Ubuntu

1. **Install build dependencies:**
   ```bash
   sudo apt update
   sudo apt install -y dotnet-sdk-6.0 git mono-complete
   ```

2. **Clone the repository:**
   ```bash
   git clone https://github.com/dandol328/RoundsWithFriendsNew.git
   cd RoundsWithFriendsNew
   ```

3. **Locate your ROUNDS install directory.** On Linux, Steam games are typically found at:
   ```
   ~/.steam/steam/steamapps/common/ROUNDS
   ```

4. **Override the ROUNDS path** by creating `RoundsWithFriends/RoundsWithFriends.csproj.user`:
   ```xml
   <Project>
     <PropertyGroup>
       <RoundsFolder>/home/YOUR_USERNAME/.steam/steam/steamapps/common/ROUNDS</RoundsFolder>
     </PropertyGroup>
   </Project>
   ```
   Replace `YOUR_USERNAME` with your actual Linux username.

5. **Build the project:**
   ```bash
   dotnet build RoundsWithFriends.sln --configuration Release
   ```
   The compiled `RoundsWithFriends.dll` will be placed in `RoundsWithFriends/bin/Release/`.

6. **Install the mod** by copying the output DLL to your BepInEx plugins directory:
   ```bash
   cp RoundsWithFriends/bin/Release/RoundsWithFriends.dll \
     ~/.steam/steam/steamapps/common/ROUNDS/BepInEx/plugins/
   ```

### Bassite OS

1. **Install build dependencies** using the Bassite package manager:
   ```bash
   sudo bassite install dotnet-sdk git mono
   ```
   If the .NET SDK is not available in the Bassite repositories, download and install it manually from [dotnet.microsoft.com](https://dotnet.microsoft.com/download) and follow the Linux install instructions for your architecture.

2. **Clone the repository:**
   ```bash
   git clone https://github.com/dandol328/RoundsWithFriendsNew.git
   cd RoundsWithFriendsNew
   ```

3. **Locate your ROUNDS install directory.** Steam games on Bassite OS are typically found at:
   ```
   ~/.steam/steam/steamapps/common/ROUNDS
   ```

4. **Override the ROUNDS path** by creating `RoundsWithFriends/RoundsWithFriends.csproj.user`:
   ```xml
   <Project>
     <PropertyGroup>
       <RoundsFolder>/home/YOUR_USERNAME/.steam/steam/steamapps/common/ROUNDS</RoundsFolder>
     </PropertyGroup>
   </Project>
   ```
   Replace `YOUR_USERNAME` with your actual username.

5. **Build the project:**
   ```bash
   dotnet build RoundsWithFriends.sln --configuration Release
   ```
   The compiled `RoundsWithFriends.dll` will be placed in `RoundsWithFriends/bin/Release/`.

6. **Install the mod** by copying the output DLL to your BepInEx plugins directory:
   ```bash
   cp RoundsWithFriends/bin/Release/RoundsWithFriends.dll \
     ~/.steam/steam/steamapps/common/ROUNDS/BepInEx/plugins/
   ```
