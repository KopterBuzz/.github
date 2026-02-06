# KopterBuzz

I am Gabor Nemeth, Endpoint Engineer during 9-5, Hobby Software Developer and general tech enthusiast otherwise.

I use this github org to host some of my projects:

## Video Game Projects
* [NOMNOM - A Centralised Registry for Nuclear Option Mod Managers](https://github.com/KopterBuzz/NOModManifestTesting)

NOMNOM is a self-updating package manifest registry that Mod Manager Applications can use to source Nuclear Option Mod Packages.
 
NOMNOM can also register mod dependencies, incompatibilities, and add-ons to other Mods such as Voice Packs etc.

* [NOBlackBox - A Tacview Exporter for Nuclear Option](https://github.com/KopterBuzz/NOBlackBox)

NOBlackBox is a [Tacview](https://www.tacview.net/) Recording utility for the multiplayer air combat game [Nuclear Option.](https://store.steampowered.com/app/2168680/Nuclear_Option/) The mod allows players and server owners to record their game session for later tactical analysis/debrief using the Tacview application.


## PSChromiumExtensionManagement

https://github.com/KopterBuzz/PSChromiumExtensionManagement

This is a PowerShell module that makes it easier to manage Chromium Browser Extension deployment & configuration on Windows with code instead of Vendor-specific configuration management or GPO. It currently supports Microsoft Edge and Google Chrome.

The goal of the module is achieved by manipulating the [Chromium ExtensionSettings Policy's](https://www.chromium.org/administrators/policy-list-3/extension-settings-full/) Registry Value directly. The code checks for common errors and attempts to prevent deploying bad configuration that would cause the browser to fail interpreting the policy.


## SCCM & Intune PowerShell Scripts

https://github.com/KopterBuzz/SCCM_Intune_PowerShell

https://github.com/KopterBuzz/IntuneRemediationScripts

I have some goodies here that I developed over the years and proved real handy.

* [Legacy LAPS Remediation](https://github.com/KopterBuzz/IntuneRemediationScripts/tree/main/Legacy%20Laps%20Remediation)
Is an Intune Remediation Script package that can assist in migrating to the new Windows LAPS by removing the Legacy LAPS Extension from Workstations that no longer require it to be installed.

* [WinGet ACL Remediation](https://github.com/KopterBuzz/IntuneRemediationScripts/tree/main/WingetACLRemediation) Is also a Remediation package, it served as a workaround for the WinGet bug that left its state folders in user profiles without SYSTEM permissions, rendering Windows unable to access these files, causing traditional methods of Stale User Profile clean-up not to work. The remediation resolves this problem by recursively re-adding permissions to the impacted paths and files.

* [Intune Onboarding Script](https://github.com/KopterBuzz/SCCM_Intune_PowerShell/tree/main/Intune%20OnBoarding%20Script) is designed to speed up the assignment of SCCM-Intune Co-Management settings. In my daily work environment we had constant issues with newly built workstations taking a long time to register with Intune. This script, when registered as a Scheduled Task on workstations as part of the provisioning process, expedites the process to such efficiency that we completely stopped getting tickets from L2 regarding this issue.

* [Stale User Profile Remover](https://github.com/KopterBuzz/SCCM_Intune_PowerShell/tree/main/StaleUserProfileRemover) is my preferred method to clean up aged user profiles from Windows Systems. It works in scenarios where security scanning that fiddles with ntuser.dat files prevents the traditional "Delete User Profiles Older Than $x Days" GPO from functioning. Instead it uses profile load time information available in the Registry. It also prevents unwanted/accidental profile deletions by automatically excluding pre-defined profiles and the currently logged on user, just to be extra sure. The script can be installed as a scheduled task using the provided installation script.
