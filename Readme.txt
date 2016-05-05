-------------------------------------------------------------------

                           DigitalPersona
                      One Touch for Windows SDK

                           Version 1.6.1
                            August 2010
				
      (c) 1996-2010 DigitalPersona, Inc. All Rights Reserved. 
-------------------------------------------------------------------

This document provides late-breaking or other information that supplements the DigitalPersona One Touch for Windows SDK documentation.


-------------------------
How to Use This Document
-------------------------

To view the Readme file on-screen in Windows Notepad, maximize the Notepad window. On the Format menu, click Word Wrap. To print the Readme file, open it in Notepad or another word processor, and then use the Print command on the File menu.


---------
CONTENTS
---------

1.   INSTALLATION
2.   COMPATIBILITY
3.   SYSTEM REQUIREMENTS
4.   RELEASE NOTES     
5.   KNOWN ISSUES      
6.   SUPPORT AND FEEDBACK

 
----------------
1. INSTALLATION
----------------

You must have local administrator rights to install this product on supported Windows systems.

One Touch for Windows SDK 1.6.1
1- Open/load the One Touch for Windows product package
2- Run Setup.exe located in the SDK folder
3- Follow the installation instructions
4- Connect the U.are.U Fingerprint Reader

One Touch for Windows RTE 1.6.1
1- Open/load the One Touch for Windows product package 
2- Run Setup.exe located in the RTE folder
3- Follow the installation instructions
4- Connect the U.are.U Fingerprint Reader


-----------------
2. COMPATIBILITY
-----------------

DigitalPersona One Touch for Windows Version 1.6.1 is compatible with the following DigitalPersona products:

- DigitalPersona Pro for AD Workstation 4.2.0 and later
- DigitalPersona Pro for AD Kiosk 4.2.0 and later

Fingerprint templates produced by the One Touch for Windows SDK are also compatible with the following DigitalPersona SDKs:

- Gold SDK
- Gold CE SDK
- One Touch for Windows SDK, all previous editions
- One Touch for Linux SDK, all distributions

Platinum SDK registration templates must be converted to a compatible format to work with these SDKs. See the Developer Guide for instructions on performing the conversion. 

DigitalPersona One Touch for Windows Version 1.6.1 is incompatible with any other DigitalPersona product.


-----------------------
3. SYSTEM REQUIREMENTS
-----------------------

- x86-based processor or better
- CD/DVD drive (for CD-ROM installation)
- JRE or JDK (1.5 or 1.6) - To run samples and completed applications if developing in Java
- USB port on the computer where the fingerprint reader is to be connected
- One of the following operating systems - Microsoft Windows XP (32/64-bit), Microsoft Windows XP Embedded (32-bit), Microsoft Windows Vista (32/64-bit), Microsoft Windows 7 (32/64-bit), Microsoft Server 2003/2008 (32/64-bit)
- DigitalPersona U.are.U 4000B or U.are.U 4500 fingerprint reader


-----------------
4. RELEASE NOTES
-----------------

4.1 Support for fingerprint authentication on a remote computer, including Citrix connections.

This version includes support for fingerprint authentication through Windows Terminal Services (including Remote Desktop Connection) and through a Citrix connection to a Metaframe Presentation Server using the Citrix Presentation Server Client package. Note however, that the client library file needed for Citrix support is not installed by default.

To deploy the DP library for Citrix support:

- Locate the DPICACnt.dll file in the product package, "Misc\Citrix Support" folder, and copy it to the folder on the client computer where the Citrix client components are located. For example, when using the Program Neighborhood client copy to the "Program Files\Citrix\ICA Client" folder. 
- Using the regsvr32.exe program, register the DPICACnt.dll library.
- If you have several Citrix clients installed on a computer, deploy the DPICACnt.dll library to the Citrix client folder for each client.

The SDK sample code can be run through Remote Desktop or a Citrix session.

The following types of Citrix clients are supported for fingerprint authentication:

- Program Neighborhood
- Program Neighborhood Agent
- Web Client

4.2 To deploy your application, you will need to include the DigitalPersona One Touch for Windows Runtime Environment (RTE) located within the "RTE" folder on the Product CD. This installs the components required to execute One Touch operations used by your application. It does not install the sample code and SDK documentation files.

4.3 In order for Pro Workstation 4.2.0 (and later) or Pro Kiosk 4.2.0 (and later) to work with an application developed with One Touch for Windows SDK 1.6.1, the Administrator needs to enable two Group Policy Objects (GPOs):"Use DigitalPersona Pro Server for authentication", "Allow Fingerprint Data Redirection" and enable "ForbidFPCompression". For more information on how to enable these policies, please see the "DigitalPersona Pro for AD Guide.pdf" located in the DigitalPersona Pro Server product package.

4.4 This product supports Windows Vista. However, developers may need to modify application and driver services to run in Windows Vista. Refer to the Microsoft document: "Impact of Session 0 Isolation on Services and Drivers in Windows Vista" included in the product package, in the Docs folder as "Session0_Vista.doc".

4.5 If you have JDK or JRE 1.5 or 1.6 installed, and do not have the JAVA_HOME environment variable defined, the setup program will automatically set the variable to the JDK or JRE root folder. For example: set JAVA_HOME=c:\Program Files\Java\jre1.6.0_03.

4.6 Silent installation requires the .NET Framework 2.0 or later. However, you can run a silent installation without the .NET Framework by modifying the InstallOnly.bat file to bypass installation of .NET components:
msiexec /i Setup.msi ADDLOCAL="FpRecLibs,ThinClientRDP,ActiveXFpRecLibs,ActiveXThinClientRDP,JavaFpRecLibs,JavaThinClientRDP" /qn /l*v c:\msi.trace.

4.7 This release adds the following features:
- Get/Set device parameter functionality. This feature is available within the C API, and referenced in the C++ version of the OTW Developer Guide. To use these parameters in .NET, request Technical Bulletin 0901, "Using the Get/Set parameter in .NET" from DigitalPersona Technical Support.
- Multi-form support in IE8 for the Verification control



----------------
5. KNOWN ISSUES 
----------------

5.1 You may be required to manually locate the usbdpfp.sys file (fingerprint reader driver) when installing this product on an XP Embedded computer. The file is located in the "\Windows\DPDrv" folder.

5.2 The Java Console sample application will not run if you have Digitalpersona Pro Workstation or Kiosk installed on the computer.

5.3 When creating your own msi installer for 64-bit application using the merge modules, you need to specify separate target directories for 32-bit and 64-bit merge modules.


------------------------
6. SUPPORT AND FEEDBACK
------------------------

Technical support is available through the DigitalPersona Developer Connection at www.digitalpersona.com/webforums, where you can search for answers to questions posted by other developers and post your own questions. You can also purchase a Developer Support package at our web store, http://buy.digitalpersona.com.

