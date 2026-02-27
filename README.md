# SMTPAuthRemediation
The goal is to scan the org for SMTP Auth being used on accounts &amp; remove the option (which defaults to modern auth)

This script will disable the legacy SMTP Auth protocol for all users (effectively forcing them toward Modern Auth or blocking them if they don't support it), while skipping the specific accounts you want to keep as-is.

Tenant-Wide Setting: You can disable SMTP Auth for the entire organization by running Set-TransportConfig -SmtpClientAuthenticationDisabled $true. The per-mailbox settings in the script above act as "exceptions" to this global rule.

The "Audit" Report: Before running this, check the SMTP AUTH Clients Report in the Exchange Admin Center (Reports > Mail flow). It shows you exactly which accounts have successfully sent mail using Basic Auth versus Modern Auth in the last 7 days.

App Passwords: If you have MFA enabled, legacy SMTP apps often use "App Passwords." Disabling SMTP Auth via this script will break those connections entirely.

# Note: Ensure you have the ExchangeOnlineManagement module installed and are connected via Connect-ExchangeOnline.  
