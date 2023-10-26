# Set-Lock-Screen-Windows-PRO-GPO

You have two options: you can either copy the background image from your server to the local computer (which is my preferred method), or you can create a direct link to the file on the server share.

(COPY)

To copy the image, create a new entry in Computer Configuration > Preferences > Windows Settings > Folders. Specify C:\Windows\Background as the destination path, and keep all other settings as their default values.

For linking directly to the file on the server share, create a new entry in Computer Configuration > Preferences > Windows Settings > Files. Enter the full path of the file on the server share in the "Source file(s)" field (e.g., \ServerName\Share\Background\LockScreen.jpg). Specify the desired path for the file on the local computer (e.g., C:\Windows\Background\LockScreen.jpg). Leave all other settings at their default values.

Create three registry entries in Computer Configuration > Preferences > Windows Settings > Registry:

1.

        Hive: HKEY_LOCAL_MACHINE

        Key Path: SOFTWARE\Microsoft\Windows\CurrentVersion\PersonalizationCSP

        Value name: LockScreenImageStatus

        Value type: REG_DWORD

        Value data: 0

        Base: Decimal
2.

        Hive: HKEY_LOCAL_MACHINE

        Key Path: SOFTWARE\Microsoft\Windows\CurrentVersion\PersonalizationCSP

        Value name: LockScreenImagePath

        Value type: REG_SZ

        Value data: C:\Windows\Background\LockScreen.jpg

3.

        Hive: HKEY_LOCAL_MACHINE

        Key Path: SOFTWARE\Microsoft\Windows\CurrentVersion\PersonalizationCSP

        Value name: LockScreenImageUrl

        Value type: REG_SZ

        Value data: C:\Windows\Background\LockScreen.jpg
