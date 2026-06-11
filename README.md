<div align="center">
  <h1>IT Automation & Systems Engineering Portfolio</h1>
  <p><i>Showcasing enterprise application deployment, advanced PowerShell tooling, and Python-driven automation.</i></p>
</div>

## 👨‍💻 About

I am an IT professional specializing in endpoint management, automation, and systems engineering. This repository serves as a portfolio of my work, highlighting my ability to streamline operations, package complex software, and build robust automation scripts.

---

## 🚀 Key Skills & Technologies

* **Endpoint Management & Packaging:** PowerShell App Deployment Toolkit (PSADT), SCCM / Intune, MSI/EXE packaging, Zero-touch Deployments
* **Scripting & Automation:** PowerShell, Python, Bash, Google Apps Script (JavaScript)
* **Data Extraction & Web Automation:** Playwright, Puppeteer, Pandas, Pyperclip, REST APIs
* **Systems Administration:** Windows Registry manipulation, WMI, Silent installation parameters, Vendor documentation scraping, MDM (Meraki) API Integration

---

## 📁 Portfolio Highlights

### 1. Advanced Engineering Solutions (PowerShell)
I specialize in solving complex deployment challenges that standard IT tools cannot handle natively. 

<details>
<summary><b>Example: Win11 Zero-Touch Hardware Bypass Upgrader</b></summary>
<br>
An advanced, zero-touch Windows 11 upgrade script that fully bypasses TPM, CPU, RAM, and Storage checks. It dynamically writes bypasses to <code>HKLM\SYSTEM\Setup\LabConfig</code>, generates a custom <code>unattend.xml</code> answer file on the fly, and hex-edits <code>setupconfig.dat</code> to spoof a "Server" installation environment. It features a robust polling mechanism for <code>SetupHost.exe</code> to ensure the silent upgrade proceeds safely.

**Business Impact:** Engineered to rapidly secure an aging device fleet against critical vulnerabilities. By temporarily forcing Windows 11 upgrades onto older hardware lacking sufficient RAM and TPM 2.0, this solution ensured immediate compliance and mitigated security risks without incurring massive, unplanned hardware replacement costs.
</details>

<details>
<summary><b>Example: Offline Registry Hive Mounter</b></summary>
<br>
A PowerShell function designed to inject POS SQL connection strings across an entire fleet. It natively iterates over every user profile on the system, explicitly loads offline <code>ntuser.dat</code> hives for logged-out profiles and the Default profile, injects the required configuration, and cleanly unloads the hives.
</details>

<details>
<summary><b>Example: YAML Parser & Deep Archive Extractor</b></summary>
<br>
Automates the deployment of nested payloads by fetching and parsing a live YAML configuration via Regex. It determines the latest installer path, downloads it, and feeds it to <code>7z.exe</code> twice—first extracting the installer contents, then locating and extracting a nested <code>.7z</code> payload hidden deep inside the <code>PLUGINSDIR</code> directly into user profiles.
</details>

### 2. Custom Web Automation & API Scraping
Leveraged Python and web automation frameworks to reverse-engineer undocumented APIs and perform bulk administration tasks.

<details>
<summary><b>Example: Dynamic Panel Management Toolkit (Python)</b></summary>
<br>
A comprehensive management script for interactive panels. It leverages an undocumented API endpoint, dynamically constructs deeply nested JSON schemas for Tag/Firmware filtering, paginates through targeted devices, and concurrently pushes batch maintenance payloads (e.g. Firmware Updates, Lock commands) to groups of 100 panels at a time.

**Business Impact:** Developed because the vendor (Newline) completely lacked a native bulk-action feature for firmware updates. This toolkit proved advanced MDM automation capabilities by enabling one-click firmware deployments across hundreds of panels simultaneously, saving weeks of manual on-site technician labor.
</details>

<details>
<summary><b>Example: Playwright & API Hybrid iPadOS Bulk Updater (Python)</b></summary>
<br>
An advanced Python automation script engineered to force iPadOS updates across an entire fleet. It pulls device IDs via the official Meraki API, uses <code>playwright.async_api</code> to spin up a Chromium browser to pass through SSO/MFA, securely captures the live session cookies and internal <code>X-CSRF-Token</code>, and then uses those credentials to send bulk POST requests to an undocumented internal endpoint.

**Business Impact:** Built to overcome severe limitations in Cisco Meraki's front-facing API, which lacked a native method to force OS updates to managed iPads. By reverse-engineering the internal dashboard API and seamlessly blending official API endpoints with headless browser request interception, this script automated critical iPad OS updates, replacing thousands of manual clicks and proving advanced ability to engineer around platform limitations.
</details>

### 3. Enterprise Application Packaging (PSADT)
Engineered a vast library of standardized deployment scripts using the **PowerShell App Deployment Toolkit**. Over the course of my career, I have successfully packaged **over 77 individual applications**, ranging from simple MSIs to complex, multi-component archaic software that natively lacked silent installation capabilities. These scripts handle pre-installation checks, process termination, custom registry modifications, and post-installation cleanup to ensure silent delivery to end-user devices.

<details>
<summary><b>Example: Custom DPI-Aware GUI for Archaic POS Software</b></summary>
<br>
A massive PSADT script I engineered to wrap an archaic Point-of-Sale (POS) software suite that lacked silent installation flags. I built a fully DPI-aware, dynamically scaling Windows Forms GUI entirely in native PowerShell (without XAML or external binaries). The GUI automatically calculated screen widths to scale text and button sizes, allowing field technicians to simply select the modular components they needed to install, completely standardizing an otherwise manual, multi-hour installation process.
</details>

<details>
<summary><b>Example: Wrapperless NSIS Deployer & Add/Remove Programs Spoofing</b></summary>
<br>
Engineered to completely bypass a vendor's mandatory GUI installer. The script queries undocumented JSON APIs to generate signed download URLs, uses 7-Zip to silently extract the NSIS installer, locates and extracts a nested `.7z` payload, and injects the raw application files directly into every existing user profile's `AppData` folder. Finally, it fabricates completely custom "Add/Remove Programs" registry entries from scratch to spoof a successful machine-wide installation.
</details>

<details>
<summary><b>Example: AppX Provisioning with Dynamic MSI Fallback</b></summary>
<br>
A bulletproof deployment workflow for modern Windows apps. It dynamically scans all user profiles to determine who is missing an AppX package, registers it for currently logged-on users using <code>Execute-ProcessAsUser</code>, and provisions it system-wide using <code>Add-AppxProvisionedPackage</code>. If the AppX installation fails or isn't found locally, it seamlessly falls back to downloading the latest legacy MSI version directly from a parsed vendor JSON manifest.
</details>

<details>
<summary><b>Example: Dynamic InstallShield Answer File Generation</b></summary>
<br>
Brilliantly bypasses the limitations of legacy InstallShield uninstallers that require static, pre-recorded answer files (`.iss`). This script dynamically discovers the legacy application's <code>ProductGuid</code> and <code>DisplayVersion</code> from the registry, then builds a custom InstallShield Answer File line-by-line on the fly. It feeds this dynamically generated file into the hidden uninstaller to force a completely silent, automated uninstallation of unknown prior versions.
</details>

* **Featured Deployments:**
  * **Creative & Design:** Adobe Creative Cloud, Autodesk AutoCAD, Autodesk Fusion, Audacity
  * **Virtualization & Remote Access:** VMware Horizon, ScreenConnect, Webex, DisplayLink Manager
  * **Education & Enterprise:** Minecraft Education, Google Drive, SMART Learning Suite, TestNav

### 4. Google Workspace & MDM Automations
Engineered automated workflows using Google Apps Script to seamlessly connect Google Workspace with MDM platforms and streamline IT operations.

<details>
<summary><b>Example: Meraki MDM Tag Provisioning via API</b></summary>
<br>
Developed custom scripts to process form submissions and dynamically update Meraki device tags via API integrations.

```javascript
function modifyTag(serial, tag, action, e) {
  // Calls the Meraki API to dynamically assign or revoke device tags based on Google Sheet approvals
  const url = `https://api.meraki.com/api/v1/networks/${NETWORK_ID}/sm/devices/modifyTags`;
  const payload = { serials: [serial], tags: [tag], updateAction: action };
  
  const options = { method: 'post', contentType: 'application/json', headers: { 'X-Cisco-Meraki-API-Key': API_KEY }, payload: JSON.stringify(payload) };
  // ...
  // Validates HTTP status codes, updates status trackers, and provides user toasts on success
}
```
*This workflow eliminated manual MDM tracking and ensured accurate role-based provisioning of resources directly from IT request forms.*
</details>

<details>
<summary><b>Example: Automated Lifecycle Communications</b></summary>
<br>
Built a script to automatically dispatch customized exit procedure instructions to departing staff, enforcing data retention policies and device return protocols without manual intervention.
</details>

---


Key Accomplishments: Security Analysis & Vulnerability Reporting

Collaborative Vulnerability Assessment: Contributed to a team-led initiative to audit critical IT infrastructure, producing technical reports for high-priority systems including CCURE, Nutrikids, and Reliable HVAC.
Infrastructure Risk Analysis: Conducted a detailed security review of the Nutrikids server environment, identifying critical risks such as manual backup dependencies and legacy database vulnerabilities.
Remediation Strategy Development: Authored strategic recommendations for system modernization, including the migration of legacy self-hosted applications to cloud-based solutions to reduce the local attack surface.
Access Control & Authentication Auditing: Evaluated system compatibility for modern security standards (SSO, MFA, and LDAPS), identifying gaps in vendor access and administrative privilege management.
Technical Security Research: Analyzed high-severity CVEs, including Remote Code Execution (RCE) in Erlang/OTP (CVSS 10.0) and privilege escalation risks in Windows service permissions.

---

## 📈 Get in Touch

Feel free to explore the scripts in this repository to see my coding style and problem-solving approach. If you are looking for an engineer who can bridge the gap between systems administration and development, let's connect!

[LinkedIn Profile](https://www.linkedin.com/in/akh073000) | [Email Me](mailto:akh073000@gmail.com)

