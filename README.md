# Registry Hacks

## Hyper-V, Windows Client
### Enable Rounded Corners on Windows 11 Virtual Machines

```
reg add HKLM\Software\Microsoft\Windows\Dwm /v ForceEffectMode /d 2 /t REG_DWORD
```

## Outlook 2016, 2019, 2021, 2024, 365 (Classic)

### Calender Permissions - Legacy UX

```
reg add HKCU\Software\Microsoft\Office\16.0\Outlook\Options\Calendar /v ShowLegacySharingUX /t REG_DWORD /d 1
```
[https://support.microsoft.com/en-us/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec]

### Deleted Items in Shared Mailbox

```
reg add HKCU\Software\Microsoft\Office\<x.0>\Outlook\Options\General /v DelegateWastbasketStyle /t REG_DWORD /d 4|8
```
4...Stores deleted items in the mailbox owners folder

8...Stores deleted items in your folder

[https://learn.microsoft.com/en-us/outlook/troubleshoot/email-management/deleted-items-go-to-wrong-folder]

### Sent Items Style Outlook

```
reg add HKEY_CURRENT_USER\Software\Microsoft\Office\x.0\Outlook\Preferences /v DelegateSentItemsStyle /t REG_DWORD /d 1
```
plus
```
set-mailbox <mailbox name> -MessageCopyForSentAsEnabled $True
set-mailbox <mailbox name> -MessageCopyForSendOnBehalfEnabled $True
```

[https://learn.microsoft.com/en-us/exchange/troubleshoot/user-and-shared-mailboxes/sent-mail-is-not-saved]
