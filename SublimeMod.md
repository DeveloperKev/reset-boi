### Note

1. If you can, please purchase the genuine license through [the official channel](https://www.sublimehq.com/store/) and support the software developer.
1. All crack methods here are implemented by [**@leogx9r**](https://gist.github.com/leogx9r).
1. **All data is not guaranteed to be authoritative or correct, nor has it been tested across the platform, nor is it responsible for any errors, lost data, etc. in practice! Please assess yourself!!!**
1. I am only within the ability to update the information based on the existing crack methods until the existing rules fail.

---

### ToC

|                | Sublime Text                                                                                                                                       | Sublime Merge   |
| -------------- | :----------: | :-------------: |
| Stable channel | <a href="#ST_SC_Win64">win</a> / <a href="#ST_SC_Linux">linux</a> / <a href="#ST_SC_macOS">mac</a> / <a href="#ST_SC_macOS_ARM64">mac-arm64</a> | <a href="#SM_SC_Win64">win</a> / <a href="#SM_SC_Linux">linux</a> / <a href="#SM_SC_macOS">mac</a> / <a href="#SM_SC_macOS_ARM64">mac-arm64</a>
| Dev channel    | <a href="#ST_DC_Win64">win</a> / <a href="#ST_DC_Linux">linux</a> / <a href="#ST_DC_macOS">mac</a> / <a href="#ST_DC_macOS_ARM64">mac-arm64</a> | <a href="#SM_DC_Win64">win</a> / <a href="#SM_DC_Linux">linux</a> / <a href="#SM_DC_macOS">mac</a> / <a href="#SM_DC_macOS_ARM64">mac-arm64</a>

---

### How to Crack Sublime Text, Stable Channel, Build 4143

Thanks to [**@leogx9r**](https://gist.github.com/leogx9r) for providing cracking methods.
> https://gist.github.com/JerryLokjianming/71dac05f27f8c96ad1c8941b88030451?permalink_comment_id=3762200#gistcomment-3762200
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3802197#gistcomment-3802197
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3803204#gistcomment-3803204

#### <div id="ST_SC_Win64">Win64</div>

Desciption                       | Offset     | Original             | Patched
-------------------------------- | :--------: | -------------------- | --
Initial License Check            | 0x000A9864 | 55 41 57 41          | 48 31 C0 C3
Persistent License Check 1       | 0x000071FE | E8 71 8B 20 00       | 90 90 90 90 90
Persistent License Check 2       | 0x00007217 | E8 58 8B 20 00       | 90 90 90 90 90
Disable Server Validation Thread | 0x000AB682 | 55 56 57 48 83 EC 30 | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x000A940F | 55                   | C3
Disable Crash Reporter           | 0x00000400 | 41                   | C3

> for 4117, 4118: https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3927712#gistcomment-3927712

##### Bat Script

```bat
:: for Win64
cd /d "C:\Program Files\Sublime Text" || exit
certutil -hashfile sublime_text.exe md5 | find /i "654F4259E066F90F4964E695CF808AD0" || exit
echo 000A9864: 48 31 C0 C3          | xxd -r - sublime_text.exe
echo 000071FE: 90 90 90 90 90       | xxd -r - sublime_text.exe
echo 00007217: 90 90 90 90 90       | xxd -r - sublime_text.exe
echo 000AB682: 48 31 C0 48 FF C0 C3 | xxd -r - sublime_text.exe
echo 000A940F: C3                   | xxd -r - sublime_text.exe
echo 00000400: C3                   | xxd -r - sublime_text.exe
```

PS：[**xxd.exe**](https://github.com/git-for-windows/git-sdk-64/raw/main/usr/bin/xxd.exe) extracted from [git for windows](https://github.com/git-for-windows/git-sdk-64)

**The license can be any string.**

Blocked by **Microsoft Defender SmartScreen** -> **More Info** -> **Run Anyway**

  <details>
    <summary>Screenshot</summary>

    ![Screenshot](https://i.imgur.com/t4QlRZ6.png)

    ![Screenshot](https://i.imgur.com/18372Rh.png)
  </details>

#### <div id="ST_SC_Linux">Linux</div>

Desciption                       | Offset     | Original             | Patched
-------------------------------- | :--------: | -------------------- | --
Initial License Check            | 0x003A31F2 | 55 41 57 41          | 48 31 C0 C3
Persistent License Check 1       | 0x00399387 | E8 08 0E 12 00       | 90 90 90 90 90
Persistent License Check 2       | 0x0039939D | E8 F2 0D 12 00       | 90 90 90 90 90
Disable Server Validation Thread | 0x003A4E30 | 55 41 56 53 41 89 F6 | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x003A2E82 | 41                   | C3
Disable Crash Reporter           | 0x0038C9F0 | 55                   | C3

##### Bash Script

```bash
# for Linux
cd /opt/sublime_text || exit
md5sum -c <<<"AFDEBB91F2BF42C9B491BAFD517C0A49  sublime_text" || exit
echo 003A31F2: 48 31 C0 C3          | xxd -r - sublime_text
echo 00399387: 90 90 90 90 90       | xxd -r - sublime_text
echo 0039939D: 90 90 90 90 90       | xxd -r - sublime_text
echo 003A4E30: 48 31 C0 48 FF C0 C3 | xxd -r - sublime_text
echo 003A2E82: C3                   | xxd -r - sublime_text
echo 0038C9F0: C3                   | xxd -r - sublime_text
```

#### <div id="ST_SC_macOS">macOS</div>

Desciption                       | Offset     | Original             | Patched
-------------------------------- | :--------: | -------------------- | --
Initial License Check            | 0x00096206 | 55 48 89 E5          | 48 31 C0 C3
Persistent License Check 1       | 0x000086A4 | E8 C5 8E 12 00       | 90 90 90 90 90
Persistent License Check 2       | 0x000086BC | E8 AD 8E 12 00       | 90 90 90 90 90
Disable Server Validation Thread | 0x0009779F | 55 48 89 E5 41 57 41 | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x00095DF0 | 55                   | C3
Disable Crash Reporter           | 0x000026A7 | 55                   | C3

##### Bash Script

```bash
# for MacOS
cd "/Applications/Sublime Text.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_text) = 70909B4BCCB3209C6F6C80122171BA84 ] || exit
echo 00096206: 48 31 C0 C3          | xxd -r - sublime_text
echo 000086A4: 90 90 90 90 90       | xxd -r - sublime_text
echo 000086BC: 90 90 90 90 90       | xxd -r - sublime_text
echo 0009779F: 48 31 C0 48 FF C0 C3 | xxd -r - sublime_text
echo 00095DF0: C3                   | xxd -r - sublime_text
echo 000026A7: C3                   | xxd -r - sublime_text
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Text.app"
```

> Requires `Apple Command Line Tools` to be installed

#### <div id="ST_SC_macOS_ARM64">macOS (ARM64)</div>

> Based on: https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3929427#gistcomment-3929427

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ------------------------| --
Initial License Check            | 0x01055A38 | E6 03 1E AA 8E 91 0E 94 | E0 03 1F AA C0 03 5F D6
Persistent License Check 1       | 0x00FE4E80 | 6E A8 03 94             | 1F 20 03 D5
Persistent License Check 2       | 0x00FE4E94 | 69 A8 03 94             | 1F 20 03 D5
Disable Server Validation Thread | 0x01056D2C | F6 57 BD A9             | C0 03 5F D6
Disable License Notify Thread    | 0x010556A0 | FC 6F BD A9             | C0 03 5F D6
Disable Crash Reporter           | 0x00FE04C0 | FC 6F BC A9             | C0 03 5F D6

##### Bash Script

```bash
# for macOS (ARM64)
cd "/Applications/Sublime Text.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_text) = 70909B4BCCB3209C6F6C80122171BA84 ] || exit
echo 01055A38: E0 03 1F AA C0 03 5F D6 | xxd -r - sublime_text
echo 00FE4E80: 1F 20 03 D5             | xxd -r - sublime_text
echo 00FE4E94: 1F 20 03 D5             | xxd -r - sublime_text
echo 01056D2C: C0 03 5F D6             | xxd -r - sublime_text
echo 010556A0: C0 03 5F D6             | xxd -r - sublime_text
echo 00FE04C0: C0 03 5F D6             | xxd -r - sublime_text
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Text.app"
```

> Requires `Apple Command Line Tools` to be installed

---

### How to Crack Sublime Text, Dev Channel, Build 4141

Thanks to [**@leogx9r**](https://gist.github.com/leogx9r) for providing cracking methods.
> https://gist.github.com/JerryLokjianming/71dac05f27f8c96ad1c8941b88030451?permalink_comment_id=3762200#gistcomment-3762200
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3802197#gistcomment-3802197
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3803204#gistcomment-3803204

#### <div id="ST_DC_Win64">Win64</div>

Desciption                       | Offset     | Original             | Patched
-------------------------------- | :--------: | -------------------- | --
Initial License Check            | 0x000A9914 | 55 41 57 41          | 48 31 C0 C3
Persistent License Check 1       | 0x000071FE | E8 41 8D 20 00       | 90 90 90 90 90
Persistent License Check 2       | 0x00007217 | E8 28 8D 20 00       | 90 90 90 90 90
Disable Server Validation Thread | 0x000AB766 | 55 56 57 48 83 EC 30 | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x000A94BF | 55                   | C3
Disable Crash Reporter           | 0x00000400 | 41                   | C3

> for 4117, 4118: https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3927712#gistcomment-3927712

##### Bat Script

```bat
:: for Win64
cd /d "C:\Program Files\Sublime Text" || exit
certutil -hashfile sublime_text.exe md5 | find /i "4CA479BCCAFE2EF69FC7F71ED4FB65C5" || exit
echo 000A9914: 48 31 C0 C3          | xxd -r - sublime_text.exe
echo 000071FE: 90 90 90 90 90       | xxd -r - sublime_text.exe
echo 00007217: 90 90 90 90 90       | xxd -r - sublime_text.exe
echo 000AB766: 48 31 C0 48 FF C0 C3 | xxd -r - sublime_text.exe
echo 000A94BF: C3                   | xxd -r - sublime_text.exe
echo 00000400: C3                   | xxd -r - sublime_text.exe
```

PS：[**xxd.exe**](https://github.com/git-for-windows/git-sdk-64/raw/main/usr/bin/xxd.exe) extracted from [git for windows](https://github.com/git-for-windows/git-sdk-64)

**The license can be any string.**

Blocked by **Microsoft Defender SmartScreen** -> **More Info** -> **Run Anyway**

  <details>
    <summary>Screenshot</summary>

    ![Screenshot](https://i.imgur.com/t4QlRZ6.png)

    ![Screenshot](https://i.imgur.com/18372Rh.png)
  </details>

#### <div id="ST_DC_Linux">Linux</div>

Desciption                       | Offset     | Original             | Patched
-------------------------------- | :--------: | -------------------- | --
Initial License Check            | 0x003A30D4 | 55 41 57 41          | 48 31 C0 C3
Persistent License Check 1       | 0x00399187 | E8 42 0E 12 00       | 90 90 90 90 90
Persistent License Check 2       | 0x0039919D | E8 2C 0E 12 00       | 90 90 90 90 90
Disable Server Validation Thread | 0x003A4CE0 | 55 41 56 53 41 89 F6 | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x003A2D64 | 41                   | C3
Disable Crash Reporter           | 0x0038C7F0 | 55                   | C3

##### Bash Script

```bash
# for Linux
cd /opt/sublime_text || exit
md5sum -c <<<"3B14994442C9BB763BC8ACC14CD9ED89  sublime_text" || exit
echo 003A30D4: 48 31 C0 C3          | xxd -r - sublime_text
echo 00399187: 90 90 90 90 90       | xxd -r - sublime_text
echo 0039919D: 90 90 90 90 90       | xxd -r - sublime_text
echo 003A4CE0: 48 31 C0 48 FF C0 C3 | xxd -r - sublime_text
echo 003A2D64: C3                   | xxd -r - sublime_text
echo 0038C7F0: C3                   | xxd -r - sublime_text
```

#### <div id="ST_DC_macOS">macOS</div>

Desciption                       | Offset     | Original             | Patched
-------------------------------- | :--------: | -------------------- | --
Initial License Check            | 0x00096A4A | 55 48 89 E5          | 48 31 C0 C3
Persistent License Check 1       | 0x00008DF4 | E8 05 90 12 00       | 90 90 90 90 90
Persistent License Check 2       | 0x00008E0C | E8 ED 8F 12 00       | 90 90 90 90 90
Disable Server Validation Thread | 0x00097FE3 | 55 48 89 E5 41 57 41 | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x00096638 | 55                   | C3
Disable Crash Reporter           | 0x00002DF7 | 55                   | C3

##### Bash Script

```bash
# for MacOS
cd "/Applications/Sublime Text.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_text) = D9F75A7113A9E2A3F88E8F6CD4AE7287 ] || exit
echo 00096A4A: 48 31 C0 C3          | xxd -r - sublime_text
echo 00008DF4: 90 90 90 90 90       | xxd -r - sublime_text
echo 00008E0C: 90 90 90 90 90       | xxd -r - sublime_text
echo 00097FE3: 48 31 C0 48 FF C0 C3 | xxd -r - sublime_text
echo 00096638: C3                   | xxd -r - sublime_text
echo 00002DF7: C3                   | xxd -r - sublime_text
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Text.app"
```

> Requires `Apple Command Line Tools` to be installed

#### <div id="ST_DC_macOS_ARM64">macOS (ARM64)</div>

> Based on: https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3929427#gistcomment-3929427

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ------------------------| --
Initial License Check            | 0x010594D4 | E6 03 1E AA 15 93 0E 94 | E0 03 1F AA C0 03 5F D6
Persistent License Check 1       | 0x00FE882C | 91 A8 03 94             | 1F 20 03 D5
Persistent License Check 2       | 0x00FE8840 | 8C A8 03 94             | 1F 20 03 D5
Disable Server Validation Thread | 0x0105A7CC | F6 57 BD A9             | C0 03 5F D6
Disable License Notify Thread    | 0x01059144 | FC 6F BD A9             | C0 03 5F D6
Disable Crash Reporter           | 0x00FE3E6C | FC 6F BC A9             | C0 03 5F D6

##### Bash Script

```bash
# for macOS (ARM64)
cd "/Applications/Sublime Text.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_text) = D9F75A7113A9E2A3F88E8F6CD4AE7287 ] || exit
echo 010595DC: E0 03 1F AA C0 03 5F D6 | xxd -r - sublime_text
echo 00FE8878: 1F 20 03 D5             | xxd -r - sublime_text
echo 00FE888C: 1F 20 03 D5             | xxd -r - sublime_text
echo 0105A8E4: C0 03 5F D6             | xxd -r - sublime_text
echo 0105924C: C0 03 5F D6             | xxd -r - sublime_text
echo 00FE3EB8: C0 03 5F D6             | xxd -r - sublime_text
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Text.app"
```

> Requires `Apple Command Line Tools` to be installed

------------------------------------------------------------------------------

### How to Crack Sublime Merge, Stable Channel, Build 2077

Thanks to [**@leogx9r**](https://gist.github.com/leogx9r) for providing cracking methods.
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3823090#gistcomment-3823090
> https://gist.github.com/JerryLokjianming/71dac05f27f8c96ad1c8941b88030451?permalink_comment_id=3762883#gistcomment-3762883
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3802197#gistcomment-3802197

#### <div id="SM_SC_Win64">Win64</div>

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x00025128 | 55 41 57 41             | 48 31 C0 C3
Persistent License Check 1       | 0x000285F3 | E8 D0 F4 26 00          | 90 90 90 90 90
Persistent License Check 2       | 0x0002860C | E8 B7 F4 26 00          | 90 90 90 90 90
Disable Server Validation Thread | 0x00026947 | 55 56 57 48 83 EC 30    | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x00024D7B | 55                      | C3
Disable Crash Reporter           | 0x0002410C | 41                      | C3

##### Bat Script

```bat
:: for Win64
cd /d "C:\Program Files\Sublime Merge" || exit
certutil -hashfile sublime_merge.exe md5 | find /i "80E989A90DFE6D9C17F4985DCEAA8942" || exit
echo 00025128: 48 31 C0 C3             | xxd -r - sublime_merge.exe
echo 000285F3: 90 90 90 90 90          | xxd -r - sublime_merge.exe
echo 0002860C: 90 90 90 90 90          | xxd -r - sublime_merge.exe
echo 00026947: 48 31 C0 48 FF C0 C3    | xxd -r - sublime_merge.exe
echo 00024D7B: C3                      | xxd -r - sublime_merge.exe
echo 0002410C: C3                      | xxd -r - sublime_merge.exe
```

PS：[**xxd.exe**](https://github.com/git-for-windows/git-sdk-64/raw/main/usr/bin/xxd.exe) extracted from [git for windows](https://github.com/git-for-windows/git-sdk-64)

#### <div id="SM_SC_Linux">Linux</div>

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x003CB652 | 55 41 57 41             | 48 31 C0 C3
Persistent License Check 1       | 0x003CE75D | E8 CE D2 1D 00          | 90 90 90 90 90
Persistent License Check 2       | 0x003CE778 | E8 B3 D2 1D 00          | 90 90 90 90 90
Disable Server Validation Thread | 0x003CCC12 | 55 41 56 53 41 89 F6    | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x003CB39E | 41                      | C3
Disable Crash Reporter           | 0x003CAFCE | 55                      | C3

##### Bash Script

```bash
# for Linux
cd /opt/sublime_merge || exit
md5sum -c <<<"189196010502F17EB99A38D8F64163BA  sublime_merge" || exit
echo 003CB652: 48 31 C0 C3             | xxd -r - sublime_merge
echo 003CE75D: 90 90 90 90 90          | xxd -r - sublime_merge
echo 003CE778: 90 90 90 90 90          | xxd -r - sublime_merge
echo 003CCC12: 48 31 C0 48 FF C0 C3    | xxd -r - sublime_merge
echo 003CB39E: C3                      | xxd -r - sublime_merge
echo 003CAFCE: C3                      | xxd -r - sublime_merge
```

#### <div id="SM_SC_macOS">macOS</div>

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x000285AD | 55 48 89 E5             | 48 31 C0 C3
Persistent License Check 1       | 0x0002AC80 | E8 56 A0 22 00          | 90 90 90 90 90
Persistent License Check 2       | 0x0002AC9F | E8 37 A0 22 00          | 90 90 90 90 90
Disable Server Validation Thread | 0x0002952F | 55 48 89 E5 41 57 41    | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x00028268 | 55                      | C3
Disable Crash Reporter           | 0x00027BE9 | 55                      | C3

##### Bash Script

```bash
# for MacOS
cd "/Applications/Sublime Merge.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_merge) = 7E05D29AF963DE90B683CA748B8A4E50 ] || exit
echo 000285AD: 48 31 C0 C3             | xxd -r - sublime_merge
echo 0002AC80: 90 90 90 90 90          | xxd -r - sublime_merge
echo 0002AC9F: 90 90 90 90 90          | xxd -r - sublime_merge
echo 0002952F: 48 31 C0 48 FF C0 C3    | xxd -r - sublime_merge
echo 00028268: C3                      | xxd -r - sublime_merge
echo 00027BE9: C3                      | xxd -r - sublime_merge
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Merge.app"
```

> Requires `Apple Command Line Tools` to be installed

#### <div id="SM_SC_macOS_ARM64">macOS (ARM64)</div>

***!!!! May have expired !!!!***

Based on:
- https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3929427#gistcomment-3929427
- for ≥ 2075: https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=4311375#gistcomment-4311375

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x014A0088 | E6 03 1E AA 98 9B 10 94 | E0 03 1F AA C0 03 5F D6
Persistent License Check 1       | 0x014A1FEC | 2A 98 06 94             | 1F 20 03 D5
Persistent License Check 2       | 0x014A2000 | 25 98 06 94             | 1F 20 03 D5
Disable Server Validation Thread | 0x014A0E0C | F6 57 BD A9             | C0 03 5F D6
Disable License Notify Thread    | 0x0149FDE0 | FC 6F BD A9             | C0 03 5F D6
Disable Crash Reporter           | 0x0149F81C | FC 6F BC A9             | C0 03 5F D6

##### Bash Script

```bash
# for macOS (ARM64)
cd "/Applications/Sublime Merge.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_merge) = 7E05D29AF963DE90B683CA748B8A4E50 ] || exit
echo 014A0088: E0 03 1F AA C0 03 5F D6 | xxd -r - sublime_merge
echo 014A1FEC: 1F 20 03 D5             | xxd -r - sublime_merge
echo 014A2000: 1F 20 03 D5             | xxd -r - sublime_merge
echo 014A0E0C: C0 03 5F D6             | xxd -r - sublime_merge
echo 0149FDE0: C0 03 5F D6             | xxd -r - sublime_merge
echo 0149F81C: C0 03 5F D6             | xxd -r - sublime_merge
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Merge.app"
```

> Requires `Apple Command Line Tools` to be installed

---

### How to Crack Sublime Merge, Dev Channel, Build 2078

Thanks to [**@leogx9r**](https://gist.github.com/leogx9r) for providing cracking methods.
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3823090#gistcomment-3823090
> https://gist.github.com/JerryLokjianming/71dac05f27f8c96ad1c8941b88030451?permalink_comment_id=3762883#gistcomment-3762883
> https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3802197#gistcomment-3802197

#### <div id="SM_DC_Win64">Win64</div>

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x000254FA | 55 41 57 41             | 48 31 C0 C3
Persistent License Check 1       | 0x000289D5 | E8 CE F7 26 00          | 90 90 90 90 90
Persistent License Check 2       | 0x000289EE | E8 B5 F7 26 00          | 90 90 90 90 90
Disable Server Validation Thread | 0x00026D65 | 55 56 57 48 83 EC 30    | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x000250FD | 55                      | C3
Disable Crash Reporter           | 0x000241A4 | 41                      | C3

##### Bat Script

```bat
:: for Win64
cd /d "C:\Program Files\Sublime Merge" || exit
certutil -hashfile sublime_merge.exe md5 | find /i "B1C0532A210A20E763D1FDCD575081EF" || exit
echo 000254FA: 48 31 C0 C3             | xxd -r - sublime_merge.exe
echo 000289D5: 90 90 90 90 90          | xxd -r - sublime_merge.exe
echo 000289EE: 90 90 90 90 90          | xxd -r - sublime_merge.exe
echo 00026D65: 48 31 C0 48 FF C0 C3    | xxd -r - sublime_merge.exe
echo 000250FD: C3                      | xxd -r - sublime_merge.exe
echo 000241A4: C3                      | xxd -r - sublime_merge.exe
```

PS：[**xxd.exe**](https://github.com/git-for-windows/git-sdk-64/raw/main/usr/bin/xxd.exe) extracted from [git for windows](https://github.com/git-for-windows/git-sdk-64)

#### <div id="SM_DC_Linux">Linux</div>

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x003CCE6A | 55 41 57 41             | 48 31 C0 C3
Persistent License Check 1       | 0x003CFE7B | E8 3C D9 1D 00          | 90 90 90 90 90
Persistent License Check 2       | 0x003CFE91 | E8 26 D9 1D 00          | 90 90 90 90 90
Disable Server Validation Thread | 0x003CE440 | 55 41 56 53 41 89 F6    | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x003CCB82 | 41                      | C3
Disable Crash Reporter           | 0x003CC5E0 | 55                      | C3

##### Bash Script

```bash
# for Linux
cd /opt/sublime_merge || exit
md5sum -c <<<"B2E180571A91852717986FED51694556  sublime_merge" || exit
echo 003CCE6A: 48 31 C0 C3             | xxd -r - sublime_merge
echo 003CFE7B: 90 90 90 90 90          | xxd -r - sublime_merge
echo 003CFE91: 90 90 90 90 90          | xxd -r - sublime_merge
echo 003CE440: 48 31 C0 48 FF C0 C3    | xxd -r - sublime_merge
echo 003CCB82: C3                      | xxd -r - sublime_merge
echo 003CC5E0: C3                      | xxd -r - sublime_merge
```

#### <div id="SM_DC_macOS">macOS</div>

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x00029017 | 55 48 89 E5             | 48 31 C0 C3
Persistent License Check 1       | 0x0002B728 | E8 DE A6 22 00          | 90 90 90 90 90
Persistent License Check 2       | 0x0002B747 | E8 BF A6 22 00          | 90 90 90 90 90
Disable Server Validation Thread | 0x00029FA7 | 55 48 89 E5 41 57 41    | 48 31 C0 48 FF C0 C3
Disable License Notify Thread    | 0x00028CA2 | 55                      | C3
Disable Crash Reporter           | 0x000284A1 | 55                      | C3

##### Bash Script

```bash
# for MacOS
cd "/Applications/Sublime Merge.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_merge) = EB2E21673517781D55DB383F90EE0844 ] || exit
echo 00029017: 48 31 C0 C3             | xxd -r - sublime_merge
echo 0002B728: 90 90 90 90 90          | xxd -r - sublime_merge
echo 0002B747: 90 90 90 90 90          | xxd -r - sublime_merge
echo 00029FA7: 48 31 C0 48 FF C0 C3    | xxd -r - sublime_merge
echo 00028CA2: C3                      | xxd -r - sublime_merge
echo 000284A1: C3                      | xxd -r - sublime_merge
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Merge.app"
```

> Requires `Apple Command Line Tools` to be installed

#### <div id="SM_DC_macOS_ARM64">macOS (ARM64)</div>

Based on:
- https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=3929427#gistcomment-3929427
- for ≥ 2075: https://gist.github.com/maboloshi/feaa63c35f4c2baab24c9aaf9b3f4e47?permalink_comment_id=4311375#gistcomment-4311375

Desciption                       | Offset     | Original                | Patched
-------------------------------- | :--------: | ----------------------- | --
Initial License Check            | 0x014AE3B0 | E6 03 1E AA 34 A0 10 94 | E0 03 1F AA C0 03 5F D6
Persistent License Check 1       | 0x014B0348 | FB 97 06 94             | 1F 20 03 D5
Persistent License Check 2       | 0x014B035C | F6 97 06 94             | 1F 20 03 D5
Disable Server Validation Thread | 0x014AF150 | F6 57 BD A9             | C0 03 5F D6
Disable License Notify Thread    | 0x014AE0EC | FC 6F BD A9             | C0 03 5F D6
Disable Crash Reporter           | 0x014AD9FC | FC 6F BC A9             | C0 03 5F D6

##### Bash Script

```bash
# for macOS (ARM64)
cd "/Applications/Sublime Merge.app/Contents/MacOS/" || exit
[ $(md5 -q sublime_merge) = EB2E21673517781D55DB383F90EE0844 ] || exit
echo 014AE3B0: E0 03 1F AA C0 03 5F D6 | xxd -r - sublime_merge
echo 014B0348: 1F 20 03 D5             | xxd -r - sublime_merge
echo 014B035C: 1F 20 03 D5             | xxd -r - sublime_merge
echo 014AF150: C0 03 5F D6             | xxd -r - sublime_merge
echo 014AE0EC: C0 03 5F D6             | xxd -r - sublime_merge
echo 014AD9FC: C0 03 5F D6             | xxd -r - sublime_merge
```

##### Re-Sign App

```bash
codesign --force --deep --sign - "/Applications/Sublime Merge.app"
```

> Requires `Apple Command Line Tools` to be installed
