# SMTPAuthRemediation
The goal is to scan the org for SMTP Auth being used on accounts &amp; remove the option (which defaults to modern auth)
This script will disable the legacy SMTP Auth protocol for all users (effectively forcing them toward Modern Auth or blocking them if they don't support it), while skipping the specific accounts you want to keep as-is.
