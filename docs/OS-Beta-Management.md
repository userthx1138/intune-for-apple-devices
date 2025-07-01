# OS Beta Management

## Prerequisites
To enroll a device in the Apple Beta Software Program or AppleSeed for IT, an MDM
solution must retrieve a token from Apple and provide it to devices during Automated
Device Enrollment or using the `com.apple.configuration.softwareupdate.settings`
declaration.

The first step is for a user with the role of administrator in Apple School Manager
or Apple Business Manager to enroll at https://beta.apple.com/for-it.

[Testing software updates with the AppleSeed for IT beta program](https://support.apple.com/en-au/guide/deployment/depe8583cf10/web)

## Obtaining the Beta Tokens
Many Device Management Services do not yet support the retrieval of Beta Enrollment tokens.

This can be achieved outside the MDM using scripting.

Neil Johnson of Microsoft has provided a script that can acheive this:

[Apple MDM Beta Token Automation](https://github.com/microsoft/shell-intune-samples/tree/master/macOS/Tools/getBetaTokens)

### Procedure

1. Download the script from github and run it in the terminal.
2. On first run the script will generate a certificate in .pem format. Copy this to a file and save it as `BetaTokensMDM.pem`
3. Log into Apple Business Manager as an Admin and create a new MDevice Management Service called `Beta Tokens MDM` and upload the `BetaTokensMDM.pem` file.
4. Download the MDM token to Downloads. The script should detect this and automatically retrive the Beta Tokens and output them to the terminal
5. Copy these tokens to a file for future reference.

## Configuring Beta Uodate Policies





