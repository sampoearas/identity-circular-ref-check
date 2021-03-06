# Identity Circular Reference Check

This package contains a SQL stored procedure for import that helps check if your system contains any circular references in the identity structure. Using the stored procedure you are able to select the amount of levels deep you would like to search to find your circular reference which will allow you clean up your identity structure.

This SQL is a modification of the Part BOM Circular Reference SQL procedure.

## History

This project and the following release notes have been migrated from the old Aras Projects page.

Release | Notes
--------|--------
[v1.0.2](https://github.com/ArasLabs/identity-circular-ref-check/releases/tag/v1.0.2) | Added Usage steps; verified on v12 
[v1.0.1](https://github.com/ArasLabs/identity-circular-ref-check/releases/tag/v1.0.1) | Verified on new versions (10+, 11+)
[v1](https://github.com/ArasLabs/identity-circular-ref-check/releases/tag/v1) | Import Package for Identity Circular Reference Check

#### Supported Aras Versions

Project | Aras
--------|------
[v1.0.2](https://github.com/ArasLabs/identity-circular-ref-check/releases/tag/v1.0.2) | 9.2.0+, 10.0+, 11.0+, 12.0+ 
[v1.0.1](https://github.com/ArasLabs/identity-circular-ref-check/releases/tag/v1.0.1) | 9.2.0+, 10.0+, 11.0+
[v1](https://github.com/ArasLabs/identity-circular-ref-check/releases/tag/v1) | 9.2.0+

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (see "Supported Aras Versions" above)
2. Aras Package Import tool
3. **IdentCircularRefCheck** import package

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\IdentCircularRefCheck\Import\imports.mf` file in the Manifest File field.
6. Select all in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

## Usage

1. Log in to Aras as admin.
2. Navigate to **Administration > SQLs** in the table of contents (TOC).
3. Search for the SQL item “SearchIdentCircularRefs” and open the stored procedure.
4. Click the More […] menu and **SQL Execute**.
   - Click **Actions > SQL Execute** in the main menu. (v11)
5. A SOAP message will display in a new tab. If the Result tag contains a value < 1, no duplicates were found and corrected.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Credits

Created by Sean Coleman for Aras Corporation Support.

## License

Published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
