<a href='#' target="_blank"><img alt='android' src='https://img.shields.io/badge/Android_Checklist-100000?style=flat-square&logo=android&logoColor=white&labelColor=8FC965&color=5D9741'/></a>
<a href='#' target="_blank"><img alt='android' src='https://img.shields.io/badge/Android-4630EB.svg?style=flat-square&logo=ANDROID&labelColor=A4C639&logoColor=fff'/></a>

# Android App Pentesting Checklist

Welcome to the "Android App Penetration Testing Checklist" repository! This repository contains a checklist of tasks and techniques that can be used to perform a comprehensive security assessment of an Android application.

The checklist covers a range of topics, including:

**Static analysis:** reviewing the app's source code and resources for potential vulnerabilities

**Dynamic analysis:** analyzing the app's behavior and interactions with the device and network during runtime

**Network analysis:** analyzing the app's communication with servers and other external resources over the network

**Permission analysis:** reviewing the app's requested permissions and assessing whether they are appropriate and secure

**Cryptographic analysis:** reviewing the app's use of cryptography and ensuring that it is implemented securely

**Data storage analysis:** analyzing the app's handling of sensitive data, including how it is stored and transmitted

This checklist is intended as a starting point for penetration testers and bug bounty hunters to identify common security issues in Android applications. It is not a comprehensive guide to all possible security issues and should be used in conjunction with other resources and best practices.

## Table of Content

- [Important Tools](#important-tools)
- [Tools Installation](#tools-installation)
  - [Prerequisites](#prerequisites)
    - [Hardware requirements](#hardware-requirements)
    - [Software/Tools prerequisites](#softwaretools-prerequisites)
      - [1. Docker (Link)](#1-docker-link)
      - [2. Android Debug Bridge (adb) (Link)](#2-android-debug-bridge-adb-link)
      - [3. Magisk (Link)](#3-magisk-link)
  - [Mobile Security Framework (MobSF)](#mobile-security-framework-mobsf)
  - [Drozer (on desktop)](#drozer-on-desktop)
- [Important Links](#important-links)
- [Intentionally Vulnerable Applications For Practice](#intentionally-vulnerable-applications-for-practice)

## Android Applications Penetration Testing Checklist (v1-beta)

| **C01** | **SSL Pinning**                                                                                                                                                                                                                                                      |       Discovered       |      Undiscovered       |
| :-----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | An SSL pinning vulnerability in an Android app occurs when the app does not properly verify the server's SSL certificate or public key during the SSL/TLS handshake process, allowing a man-in-the-middle attacker to intercept and decrypt the app's communication. |                        |                        |
|    1    | Missing SSL Pinning                                                                                                                                                                                                                                                  | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check if is it bypassable or not using Frida/Objection                                                                                                                                                                                                               | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check code manipulation possible or not                                                                                                                                                                                                                              | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C02** | **Root Detection**                                                                                                                                                                                                             |       Discovered       |      Undiscovered       |
| :-----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------: | :--------------------: |
|         | A root detection vulnerability in an Android app occurs when the app does not properly detect and prevent access by rooted devices, allowing users to potentially gain unauthorized access to the app's data or functionality. |                        |                        |
|    1    | Missing Root Detection                                                                                                                                                                                                         | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check if is it bypassable or not using frida/Objection                                                                                                                                                                         | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check that internal logic flow can be modified or not                                                                                                                                                                          | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C03** | **Emulator Detection**                                                                                                                                                                                                           |       Discovered       |      Undiscovered       |
| :-----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | An emulator detection vulnerability in an Android app occurs when the app does not properly detect and prevent access by emulators, allowing users to potentially bypass security controls or access unauthorized functionality. |                        |                        |
|    1    | Missing Emulator Detection                                                                                                                                                                                                       | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check if is it bypassable or not using frida                                                                                                                                                                                     | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C04** | **Sensitive data in ADB Logcat Logs**                                                                                                                                                                                                                                    |       Discovered       |      Undiscovered       |
| :-----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------: | :--------------------: |
|         | A sensitive data in ADB Logcat vulnerability in an Android app occurs when the app logs sensitive data, such as passwords or personal information, to the system log using Android Debug Bridge (ADB), potentially exposing the data to attackers or unauthorized users. |                        |                        |
|    1    | Check Logcat logs for sensitive information/data                                                                                                                                                                                                                         | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check if is it bypassable or not using frida/Objection                                                                                                                                                                                                                   | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check for any unencrypted request/data in Logcat logs                                                                                                                                                                                                                    | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C05** | **Sensitive data/info stored in Local Storage**                                                                                                                                                                                                                                           |       Discovered       |      Undiscovered       |
| :-----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | A sensitive data stored in local storage vulnerability in an Android app occurs when the app stores sensitive data, such as passwords or personal information, in unencrypted or unsecured local storage on the device, potentially exposing the data to attackers or unauthorized users. |                        |                        |
|    1    | Check for sensitive information/data store on Shared Preferences or not                                                                                                                                                                                                                   | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for any information/data stored in temporary files or not                                                                                                                                                                                                                           | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check if sensitive information/data is stored in the local storage database using strong encryption on or not                                                                                                                                                                             | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    4    | Check for any information/data stored in any other files or not                                                                                                                                                                                                                           | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C06** | **Sensitive data/info in Application Memory**                                                                                                                                                                                                                                                                          |       Discovered       |      Undiscovered       |
| :-----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | A sensitive data in application memory vulnerability in an Android app occurs when the app stores sensitive data, such as passwords or personal information, in memory in an unencrypted or unsecured manner, potentially exposing the data to attackers or unauthorized users who have access to the device's memory. |                        |                        |
|    1    | Check for any sensitive information/data temporarily stored on Application Memory or not[ Use fridump.py (https://github.com/Nightbringer21/fridump/blob/master/fridump.py) ]                                                                                                                                          | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C07** | **Weak Signer Certificate**                                                                                                                                                                                                              |       Discovered       |      Undiscovered       |
| :-----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | A weak signer certificate vulnerability in an Android app occurs when the app is signed with a weak or compromised certificate, potentially allowing attackers to modify the app or gain unauthorized access to the app's functionality. |                        |                        |
|    1    | Check if the app signed with a weak algorithm such as "SHC1withRSA"                                                                                                                                                                      | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for Janus Vulnerability                                                                                                                                                                                                            | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check for the application if is it signed with debug certificate or not                                                                                                                                                                  | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C08** | **Vulnerable Android Activities**                                                                                                                                                                                                                                                                                                                                                            |       Discovered       |      Undiscovered       |
| :-----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Android activities are components of an Android app that represent a screen or part of the app's user interface. A vulnerable Android activity is one that contains vulnerabilities, such as insecure coding practices or the use of third-party libraries with known vulnerabilities, that could be exploited by attackers to gain unauthorized access to the app's data or functionality.  |                        |                        |
|    1    | Check for the protected activity that can be accessible by calling the activity from the ADB bypassing the Authentication activity (Authentication Bypass)Example: An application having a login screen if login is successful the app launch the second activity, and any user has to authenticate herself. But that can bypass though ADB by calling the second activity directly from ADB | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for exported android activity is set false, and check for the android activity can activity can be launched by any other applications or not                                                                                                                                                                                                                                           | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check if any of the application activities can be hijacked through ADB or any others tools                                                                                                                                                                                                                                                                                                   | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    4    | Check if any of the application activities cause the Denial of Service or App crash                                                                                                                                                                                                                                                                                                          | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C09** | **WebView**                                                                                                                                                                                                              |       Discovered       |      Undiscovered       |
| :-----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------: | :--------------------: |
|         | Android WebView is a component of an Android app that allows the app to display web content within the app's user interface. It can contain vulnerabilities, such as insecure coding practices improper validation, etc. |                        |                        |
|    1    | Check for Cross sites scripting vulnerability in android activity WebView                                                                                                                                                | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for Local File Inclusion (LFI) vulnerability in android activity WebView                                                                                                                                           | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check for insecure JavaScript enabled for WebView                                                                                                                                                                        | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C10** | **Intent Filters**                                                                                                                                                                                                                                                                                             |       Discovered       |      Undiscovered       |
| :-----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Intent redirection is an embedded intent it can be implicit or explicit Intent which is used to move one android component to another component. This vulnerability occurs when the developer does not retrieve the intent data via filtering. This vulnerability is similar to OpenRedirect for web security. |                        |                        |
|    1    | Check for intent spoofing or intent sniffing vulnerabilities (those can occur when the developer does not retrieve the intent data via filtering)                                                                                                                                                              | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C11** | **Broadcast Receivers**                                                                                                                                                                                                                     |       Discovered       |      Undiscovered       |
| :-----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | A vulnerable Android Broadcast Receiver is a component of an Android app that allows the app to receive and respond to system-wide broadcasts, such as the receipt of a text message or the disconnection of a charger. It can be exploited |                        |                        |
|    1    | Check the manifest file for the receiver tag and the exported attribute if it is True and if there is no other permission is set. It can be exploited.                                                                                      | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C12** | **Content Provider**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |       Discovered       |      Undiscovered       |
| :-----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------: | :--------------------: |
|         | Content providers in Android are used to share data between applications. They use standard insert, update, delete, and query methods to access data and are assigned a special URI starting with "content://". If proper security controls are not implemented, it can lead to the leakage of information. An example of a content provider is the built-in SMS application, which can be accessed by other apps using a specific URI and the READ_SMS permission. There may be cases where content providers are not implemented for sharing data or where access is restricted to apps with proper permissions. |                        |                        |
|    1    | If security controls are not properly implemented, content providers can lead to SQL injection.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | If security controls are not properly implemented, content providers can lead to Path Traversal.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | If security controls are not properly implemented in content providers, it may lead to internal data access vulnerability                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C13** | **Source Code Obfuscation**                                                                                                                                                                                                  |       Discovered       |      Undiscovered       |
| :-----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Source code obfuscation in Android is the process of making the source code of an Android app difficult to understand or reverse engineer, typically to protect intellectual property or prevent unauthorized modifications. |                        |                        |
|    1    | Check for Code Obfuscation(PRO Guard) implemented or not                                                                                                                                                                     | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | If Code Obfuscation is implemented partially check for the main sensitive codes is properly obfuscated                                                                                                                       | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C14** | **Sensitive Information/Auth-Keys Hardcoded**                                                                                                                                                                                                                          |       Discovered       |      Undiscovered       |
| :-----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Hardcoded information vulnerability is the practice of storing sensitive data, such as passwords or security keys, directly in the source code of an application, potentially exposing the data to attackers or unauthorized users who have access to the source code. |                        |                        |
|    1    | Check the Source Code for any hardcoded API Key/Token, Auth-Key, Passwords, Credentials, etc.(This task can be automated by using tools like MobSF)                                                                                                                    | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C15** | **Insecure Coding Practice**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |       Discovered       |      Undiscovered       |
| :-----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Insecure coding practice refers to the use of coding techniques or practices that do not adequately protect an application or system from security vulnerabilities or threats, such as using weak passwords or failing to properly validate user input. Insecure coding practices can make an application or system more susceptible to attacks or data breaches. To prevent insecure coding practices, developers should follow best practices for secure coding and regularly review and test their code for vulnerabilities. |                        |                        |
|    1    | Check for use of Insecure Random Number Generator functions (Like generating guessable OTP)                                                                                                                                                                                                                                                                                                                                                                                                                                     | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for use of Insecure functions or insure functions/objects calling                                                                                                                                                                                                                                                                                                                                                                                                                                                         | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Uses of weak cryptography or easily reversible encryption method (like MD5 Hash, Base64 Encoding)                                                                                                                                                                                                                                                                                                                                                                                                                               | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    4    | Check for any other Insecure Coding Weakness presence                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C16** | **Insecure Deeplinks**                                                                                                                                                                                                      |       Discovered       |      Undiscovered       |
| :-----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Insecure deeplinks in Android can allow attackers to access sensitive data or functionality within an app. Developers can prevent this by validating and securing deeplinks and implementing appropriate security controls. |                        |                        |
|    1    | Check for any explicit deeplink that PendingIntent to a specific location within the application                                                                                                                            | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for any implicit deeplink that refers to a specific destination in an app when the deeplink is invoked                                                                                                                | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C17** | **Missing Integrity Checks**                                                                                                                                                                                                                                                                                                                                                 |       Discovered       |      Undiscovered       |
| :-----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Integrity checks in Android refer to the process of verifying the authenticity or integrity of an app's source code, to ensure that it has not been tampered with or modified by an unauthorized party. This can help protect against attacks that aim to inject malicious code or modify the app's functionality, such as man-in-the-middle attacks or repackaging attacks. |                        |                        |
|    1    | Decompile the application, modify its code, recompile it, and sign it to check if it still functions properly or not.                                                                                                                                                                                                                                                        | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C18** | **Insecure Android Permissions**                                                                                                                                                         |       Discovered       |      Undiscovered       |
| :-----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Android applications have a number of permissions that can be set in the "AndroidManifest.xml" file. If these permissions are not properly filtered or validated, they can be exploited. |                        |                        |
|    1    | Check for clear text traffic option enable or not in "AndroidManifest.xml" file                                                                                                          | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for debug mode option enable or not in "AndroidManifest.xml" file                                                                                                                  | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Check for backup mode option enable or not in "AndroidManifest.xml" file                                                                                                                 | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    4    | Check for any other Unnecessary Permission in "AndroidManifest.xml" file                                                                                                                 | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C19** | **Background Screen Caching**                                                                                   |       Discovered       |      Undiscovered       |
| :-----: | --------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Screen caching is a mobile vulnerability, caused due to a performance/usability feature present in mobile OS’s. |                        |                        |
|    1    | Check for screenshots are taken when the application is sent to background                                      | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C20** | **Insecure Firebase Database**                                                                                                                                  |       Discovered       |      Undiscovered       |
| :-----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Firebase Database is a cloud-based real-time database service that allows developers to store and sync data across multiple devices and platforms.              |                        |                        |
|    1    | Append ".json" payload at the end of Firebase instance to see if "read" permission are enable or not                                                            | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Also try replacing "firebaseio.com" with "appspot.com" with "/.json" appended at the end may allow you to access appspot instance. (Check for CORS in Firebase) | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C21** | **Android Lock/Biometric Authentication Bypass**                                                                                                                                        |       Discovered       |      Undiscovered       |
| :-----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Some applications use the Android Screen Lock/Biometric Authentication to validate the user before providing any specific service or before launching the application's main interface. |                        |                        |
|    1    | If the application uses Android Lock/Biometric Authentication check for that can be bypassed or not in runtime by runtime hooking or code level modification                            | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C22** | **Key-Checks in Dynamic Analysis**                                                                                                                                                      |       Discovered       |      Undiscovered       |
| :-----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------: |
|         | Some applications use the Android Screen Lock/Biometric Authentication to validate the user before providing any specific service or before launching the application's main interface. |                        |                        |
|    1    | Checks for all possible the possible test cases that’s are applicable on API Check (Use a comprehensive API checklist)                                                                  | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    2    | Check for Broken Access Controls and Authentications (Checks mainly in server side)                                                                                                     | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    3    | Checks for Server-Side Injections and Security misconfigurations                                                                                                                        | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    4    | Check for Sensitive Data exposer                                                                                                                                                        | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |
|    5    | Fuzzing                                                                                                                                                                                 | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> |

| **C-** | **Some Other Checks**                                                                                            |       Discovered       |         Undiscovered          |
| :----: | ---------------------------------------------------------------------------------------------------------------- | :--------------------: | :--------------------------: |
|        | N/A                                                                                                              |                        |                              |
|   1    | Check for the application doesn't reuse the same cryptographic key for multiple purposes                         | <ul><li>[ ] </li></ul> |    <ul><li>[ ] </li></ul>    |
|   2    | Check for any sensitive data or information exposed through the user interface or leaks to screenshots or not    | <ul><li>[ ] </li></ul> |    <ul><li>[ ] </li></ul>    |
|   3    | Check for whether the keyboard cache for the application is disable or not                                       | <ul><li>[ ] </li></ul> |    <ul><li>[ ] </li></ul>    |
|   4    | Check the application does not allow users to copy/paste any secret data (like passwords, credit card info, etc) | <ul><li>[ ] </li></ul> |    <ul><li>[ ] </li></ul>    |
|   5    | Check if the sensitive data is not masked when performing app switching                                          | <ul><li>[ ] </li></ul> |    <ul><li>[ ] </li></ul>    |
|   6    | Check for the Third-Party Keyboard applications that are disabled specifically in the sensitive fields           | <ul><li>[ ] </li></ul> | <ul><li>[ ] </li></ul> - [ ] |

**NB:** This list does not follow the OWASP vulnerability indexing order.

## Important Tools

- Mobile Security Framework (MobSF) [(Link)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
- Runtime Mobile Security (RMS) [(Link)](https://github.com/m0bilesecurity/RMS-Runtime-Mobile-Security)
- Pen-Andro [(Link)](https://github.com/raoshaab/Pen-Andro)
- Burp Suite [(Link)](https://portswigger.net/burp)
- Postman [(Link)](https://www.postman.com) `for API's`
- Yaazhini [(Link)](https://www.vegabird.com/yaazhini/)
- House [(Link)](https://github.com/nccgroup/house/)
- Apktool [(Link)](https://ibotpeaches.github.io/Apktool/)
- Easyapktool [(Link)](https://forum.xda-developers.com/t/discontinued-windows-apk-easy-tool-v1-60-2022-06-23.3333960/) `Discontinued`
- APKToolGUI(New) [(Link)](https://github.com/AndnixSH/APKToolGUI) `Easyapktool Alternative`
- Genymotion [(Link)](https://www.genymotion.com)
- Frida [(Link)](https://frida.re)
- Magisk-Frida [(Link)](https://github.com/ViRb3/magisk-frida)
- Drozer [(Link)](https://github.com/WithSecureLabs/drozer)
- Objection [(Link)](https://github.com/sensepost/objection)
- JD-GUI [(Link)](http://java-decompiler.github.io)
- JADX [(Link)](https://github.com/dwisiswant0/apkleaks)
- ApkLeaks [(Link)](https://github.com/dwisiswant0/apkleaks)
- Fridump [(Link)](https://github.com/Nightbringer21/fridump)
- Sqlite Browser [(Link)](https://sqlitebrowser.org)
- ADB [(Link)](https://developer.android.com/tools/adb)

## Tools Installation

### Prerequisites

#### Hardware requirements

- Windows/Linux (preferred Kali-Linux).
- An android device with Bootloader unlocked
  - How to unlock Bootloader ? [(Link)](https://xdaforums.com/t/how-to-unlock-bootloader.4244757/)

<!-- - , and USB debugging enabled.
  - How to enable USB debugging (Leave; it's not for you)
- Additional settings (optional)
  - test  -->

#### Software/Tools prerequisites

Before you start testing Android apps, make sure to install the necessary tools on both your computer (Linux/Windows) and the Android device itself.

##### 1. Docker [(Link)](https://www.docker.com)

**Docker installation for Debian or Ubuntu based linux distributions:**

```bash
sudo apt-get -y install docker.io
```

```bash
systemctl start docker
```

**NB:** If you are using other than Debian or Ubuntu based Linux, read this [instruction](https://docs.docker.com/get-docker) to install docker according to your operating system.

**Docker installation for Windows:**

- Download Docker Desktop [(Link)](https://www.docker.com/products/docker-desktop/)
- Double click to install

##### 2. Android Debug Bridge (adb) [(Link)](https://developer.android.com/tools/adb)

**adb installation for Debian or Ubuntu based linux distributions:**

```bash
sudo apt install adb
```

```bash
wget -c https://dl.google.com/android/repository/platform-tools-latest-linux.zip
```

```bash
unzip platform-tools-latest-linux.zip
```

```bash
cd platform-tools
```

give executable permission

```bash
chmod +x ./adb
chmod +x ./fastboot
```

Check adb working or not

```bash
./adb version
```

**adb installation for Windows:**

- Download [adb-setup.zip](https://androidfilehost.com/?fid=24686681827312411)
- Extract the downloaded zip
- Double click on adb-setup-1.4.3.exe
- In CMD window select Y for all options
![Fastboot](https://github.com/Hrishikesh7665/Android-Pentesting-Checklist/blob/extras/Fastboot.png?raw=true)
- Install the Google USB driver. (The installer will automatically run once the fastboot setup is complete)
![Google Driver](https://github.com/Hrishikesh7665/Android-Pentesting-Checklist/blob/extras/Google%20Driver.png?raw=true)

##### 3. Magisk [(Link)](github.com/topjohnwu/Magisk)

**Pre-requirement:**

- An android device with Bootloader unlocked

**Magisk installation for unlocked bootloader devices:**

1. **Install custom recovery**
   - Download a custom recovery for your Android device, such as [TWRP](https://twrp.me) / [OrangeFox](https://orangefox.download) / [PitchBlack](https://pitchblackrecovery.com) onto your desktop.
   - Rename the downloaded recovery (.img) filename to "recovery.img" (without quote)
   - Enable usb debugging on your android device
   - Run this command to check your device is connected or not

      ```cmd
      adb devices
      ```

   <!-- - Allow usb debugging authorization prompt on android
      ![USB Debugging Authorization Dialog](https://i.stack.imgur.com/yhhHf.png) -->

<!-- A rooted android device with [Magisk](https://github.com/topjohnwu/Magisk/releases) version 24 or latest installed.

   <b>Magisk installation for unlocked bootloader devices</b>

   - Download a custom recovery [TWRP](https://twrp.me)/[OrangeFox](https://orangefox.download)/[PitchBlack](https://pitchblackrecovery.com) for your android device.
   - Rename the downloaded recovery (.img) filename to recovery.img
   - Enable usb debugging on your android device
   - Run this command to check your device is connected or not

   ```
   adb devices
   ```
   - Allow usb debugging authorization prompt on android
   - Run the command to initiate a reboot into fastboot mode

   ```
   adb reboot bootloader
   ```

   - Run command to check your device is connected in fastboot mode or not

   ```
   fastboot devices
   ```

   - Flash the recovery image

   ```
   fastboot flash recovery recovery.img
   ```

   - Once TWRP is successfully flashed on your device

   ```
   fastboot reboot
   ``` -->


### Mobile Security Framework (MobSF)

<b>Pre-requirement:</b>

- Docker [(Link)](https://www.docker.com)

if you don't have docker installed on your system read this [instruction](https://docs.docker.com/get-docker/) to install docker according to your operating system.

let's assume your docker engine up and running let's

<b>Install MobSF:</b>

```
docker pull opensecurity/mobile-security-framework-mobsf
```

<b>Run MobSF:</b>

```
docker run -it --rm --name mobsf -p 8000:8000 opensecurity/mobile-security-framework-mobsf
```

Congratulation your MobSF is installed and running navigate to [localhost:8000](http://localhost:8000) using your preferred web browser.

### Drozer (on desktop)

<b>Pre-requirement:</b>

- Docker [(Link)](https://www.docker.com)

if you don't have docker installed on your system read this [instruction](https://docs.docker.com/get-docker/) to install docker according to your operating system.

let's assume your docker engine up and running let's

<b>Install Drozer:</b>

```
docker pull fsecurelabs/drozer
```

<b>Run Drozer:</b>

```
docker run -it --rm --name drozer fsecurelabs/drozer
```

Congratulation your Drozer is installed on your desktop now we need to install Drozer Agent Apk [agent-debug.apk](https://github.com/WithSecureLabs/drozer-agent/releases)

## Important Links

- [https://book.hacktricks.xyz/mobile-pentesting/android-checklist](https://book.hacktricks.xyz/mobile-pentesting/android-checklist)
- [https://owasp.org/www-project-mobile-security-testing-guide/](https://owasp.org/www-project-mobile-security-testing-guide/)
- [https://github.com/B3nac/Android-Reports-and-Resources](https://github.com/B3nac/Android-Reports-and-Resources)
- [https://github.com/wtsxDev/android-security-list](https://github.com/wtsxDev/android-security-list)
- [https://mobile-security.gitbook.io/mobile-security-testing-guide/](https://mobile-security.gitbook.io/mobile-security-testing-guide/)
- [https://github.com/ashishb/android-security-awesome](https://github.com/ashishb/android-security-awesome)

## Intentionally Vulnerable Applications For Practice

- Damn Insecure and vulnerable App for Android (DIVA) [(Link)](https://github.com/payatu/diva-android)
- InsecureBankv2 [(Link)](https://github.com/dineshshetty/Android-InsecureBankv2)
- VyAPI [(Link)](https://github.com/appsecco/VyAPI/) `Hybrid (Cloud + Android)`
- Damn Vulnerable Hybrid Mobile App (DVHMA) [(Link)](https://github.com/logicalhacking/DVHMA)
- What a Terrible Failure (WaTF Bank) [(Link)](https://github.com/WaTF-Team/WaTF-Bank)
- Vuldroid [(Link)](https://github.com/jaiswalakshansh/Vuldroid)
- Oversecured Vulnerable Android App (OVAA) [(Link)](https://github.com/oversecured/ovaa) `Raw Code(Gradle)`

<br/>
<br/>

**I tried my best to enrich this checklist. Please feel free to share your key findings and knowledge. Thank you🙏**
