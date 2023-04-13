 <h1 align="center">Yubico CSV Conversion Tool For Duo</h1>

**Yubico CSV Conversion Tool For Duo** is a Powershell script that allows you to generate CSV files in a CSV format [that Duo will accept](https://duo.com/docs/yubikey) for import using "Yubico Format" CSV files. 

* Non Destructive! - Original source material is **not** modified with this script.
* Scaleable! This script is performant even with CSV files containing 100K+ entries.
* Fast. Convert your file and be on your way.

![](/Images/conversion.png)
## 💻 Requirements
- Any operating system capable of running [Powershell](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell?view=powershell-7.3)  (Windows, Linux, macOS)
- While this script runs on virtually any version of Powershell, it is the most performant when running on Powershell 7+.
- A CSV file to use. You may have recieved one from the Yubico Production Team via a Custom Configuration order, or you may have used the Yubico Personalization Tool.

## 🐻 Security Notes
- As a general rule of thumb, **never** run Powershell scripts that you do not understand. Always feel free to review this script for yourself and ask questions in the form of a [GitHub Issue](https://github.com/chris-streeks/Yubico_CSV_Conversion_Tool_For_Duo/issues)

- For safety, I recommend that you run this script on a secure machine, taking care to delete or securely store the CSV file once you are done uploading it to Duo. This script **does not** require network access.

- For clarity on Powershell's default script execution policies, [please review the Microsoft documentation](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7)
.

## 📖 How to Use
1. Launch `Yubico_CSV_Conversion_Tool_For_Duo.ps1` 
2. Follow the prompt to select or define the location of the CSV file you wish to convert
3. Review the location of the CSV file to convert and the location of the converted file, then press Enter to start
4. There will be a CSV file in the same directory as the original file entitled `<sourcematerial>_ConvertedForDuo.CSV`.
5. [Upload this file to Duo](https://duo.com/docs/yubikey#add-token-in-duo-admin-panel)

## 🐼 Additional Notes
- A Yubico Format CSV file looks like this

`7538154,ejfhcciecgul,ea8d4cf9b363,aa4badc32d149a4c5df0612d278e28e1,000000000000,2023-04-13T11:53:36,`

This equates to...

`Serial Number, Public ID, Private ID, Seed Value, Access Code, Timestamp`


- Conversely, a Duo formatted CSV file looks like this

`ejfhcciecgul,ea8d4cf9b363,aa4badc32d149a4c5df0612d278e28e1,`

Which in English, looks like the following

`Public ID, Private ID, Seed Value,`

This script is designed to create a Duo appropriate CSV file by copying the second, third and fourth columns of each CSV line into a new file.
