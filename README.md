# Release v5.0.0 build(27534)
In this release, licensing has been changed from computer based to user based allowing users to sign in to CrescentLink with a pre-assigned GEOGRAPH account. The CrescentLink code base now targets .Net 4.7.2 (461808), and Project Planner and Network Manager extensions have been merged into one extension named CrescentLink. 

## Software Compatibility
- This release is compatible with ArcGIS Desktop versions 10.3.1 - 10.8.
- The .NET Framework v4.7.2 is required.

## Network Manager
- Fixed an issue where a layer with a broken data source could cause CrescentLink to stop looking for layers after that layer in the TOC when searching for the workspace.
- Fixed an issue in coax design power calculations where power on the main output of a splitter would sometimes not be calculated if the power was fed from a child branch of the splitter.
- Fixed an issue with branches on actives where BRANCH ports continued to use the main output value rather than the auxiliary output values.
- Updated Coax Tap calculations to give the tap score the highest priority, then the tap value next.
- Updated coax cache for better management across the system when various events occur.
- Fixed a bug that prevented specification settings from updating in a design when the active coax design profile was changed, not allowing the new specifications under the selected profile to be used in place of the old profile settings.
- Fixed a bug that could cause the Connector Tool to draw a connection line to an incorrect patched port causing confusion visually in the display if the ports were created out of order during port configuration for equipment.
- Resolved an issue with Coax Cache where a stack overflow could happen if a layer with a broken data source is in the map causing arcmap to crash when opening the MXD.
- Added the number of attachments beside the attachment buttons in Network Manager.
- Fixed a bug in Work Order Manager where a cable with an invalid subtype code would disrupt the loading process causing some features not to be displayed in the work order manager.
- Added a message to indicate if the coax junction subtype code of 30 subtype is missing from the sdm_splicepoint subtypes causing coax design items not to be placed in the map
- Fixed an issue with work order manager where changing the status on fiber equipment would cause the equipment's stationid to be reset to the value of the parent splice point's stationid. (#1287)
- Fixed a bug where auxiliary outputs on actives in coax design specifications were not used in design calculations, only the main output was used. (#853)
- Fixed a bug where active outputs always used the maximum output for signal regardless of the input + gain values in a coax design. (#1000)
- Updated the coax design tool to default the feature status of items placed in the map from the designer to 11-Proposed.
- Fixed a bug where branch swapping in the coax design tool would not properly recalculate signals when swapping back to the original branches. (#1330)
- Added the ability to right-click a result when using the CrescentLink Search tool to view that result in the Network Manager window.
- Added the ability to create a new coax design profile from an existing profile, including parameters and specifications associated with it.
- Fixed an issue with power calculations within the coax design tool that would cause calculations to stop on design items without a valid specification.
- Fixed an issue with coax design tap specifications where banks were not being filtered out based on the active design profile in the tap properties form.
- Increased performance in Coax Design tool and updated the progress dialog to display more informative information when loading a design.
- Updated Fiber Node design items so that they no longer have a main output and to only use the 4 auxiliary outputs in a coax design.
- Fixed the calculated taps so that self-terminating taps are no longer placed in the midspan of a coax design. These will now only be placed at the end of a branch.
- Increased the performance of loading an existing coax network from features in the map as a new design draft in the Coax Design tool.

## Project Planner
- Resolved an issue with the workspace cache and how the cache was not clearing properly when the version was changed.
- Added the 'arcpy.SetLogHistory(False)' python script setting to disable geoprocessor history logging on all PDF export scripts to help improve performance.
- Saving the export settings used during the last PDF export in addition to the  last sheet layout placed in the map and the last selected vendor and rate sheet  used in the Project Planner unit catalog
- Marked the Default 11x17 sheet layout option in Project Planner as Deprecated in favor of the more versatile Custom layout option. Custom layouts will be the only sheet layout option in future releases of CrescentLink.
- Added the ability to include a unit summary page with Custom sheet PDF exports based on the current documents layout page size.Added the option to toggle on/off part number, account code, total waste, and total used columns from the tally grid on Custom sheet PDF exports. Also decreased the column sizes slightly for better use of space.
- Updated the sheet export to exclude operations from the tally grid with no units assigned to them. (#1282)
- Updated the sheet export to sort operation headers in the tally grid ascending by operation number. (#1282)
- Updated the PDF export to better handle rasterization and to disable font smoothing for better compatibility with Windows 10 ClearType. (#1295)
