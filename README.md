# i928 LineageOS 22.2 OTA feed

`builds/<device>.json` is the update feed for LineageOS's Updater
(`org.lineageos.updater`), set per device with `lineage.updater.uri`:

    https://raw.githubusercontent.com/i928/OTA/lineage-22.2/builds/{device}.json

Format (LineageOS, not Evolution X):

    {"response": [{"datetime": <ro.build.date.utc of the build>,
                   "filename": "lineage-22.2-...-UNOFFICIAL-<device>.zip",
                   "id": "<sha256 of the zip>", "romtype": "UNOFFICIAL",
                   "size": <bytes>, "url": "<SourceForge .../download link>",
                   "version": "22.2"}]}

Written and pushed by `~/bin/deploy_lineage_ota.sh` (github.com/i928/bin).
The Evolution X feed lives on branch `bka`.
