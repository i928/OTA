# i928 LineageOS 23.2 OTA feed

`builds/<device>.json` is the update feed for LineageOS 23's Updater
(`org.lineageos.updater`), set per device with `lineage.updater.uri`:

    https://raw.githubusercontent.com/i928/OTA/lineage-23.2/builds/{device}.json

Format (LineageOS 23 / download API v2 -- a JSON list, not {"response": ...}):

    [{"datetime": <ro.build.date.utc of the build>, "type": "UNOFFICIAL",
      "version": "23.2",
      "files": [{"filename": "lineage-23.2-...-UNOFFICIAL-<device>.zip",
                 "sha256": "<sha256 of the zip>", "size": <bytes>,
                 "url": "<SourceForge .../download link>",
                 "os_sdk_level": 36, "os_patch_level": "YYYY-MM-DD",
                 "ota_property_files": "<A/B only>"}]}]

os_sdk_level is required in practice: missing, it counts as 0 and the Updater
drops the build as "older than current Android version".

`changelogs/<device>.txt` is what the Updater's Changelog menu opens (device
tree overlay). Both are written and pushed by `~/bin/deploy_ota.sh`
(github.com/i928/bin). LineageOS 22.2: branch lineage-22.2; Evolution X: bka.
