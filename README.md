# Changes

- Toggled on Doze support for better battery life with GCM
- Updated GmsCore to v0.2.7.17455-mapbox

# Original README:

This is a community supported repo to support integration of [microG](https://microg.org/) with RattlesnakeOS. The author of RattlesnakeOS doesn't recommend the use of microG, but since it's a highly requested feature I wanted to at least host it in a known place where others can help contribute. It is currently the required signature spoofing patch and just a subset of prebuilt packages from here: https://github.com/lineageos4microg/android_prebuilts_prebuiltapks.

## How to
Add the following to end of your `rattlesnakeos-stack` config file.
```
[[custom-patches]]
patches = ["00002-microg-sigspoof.patch"]
repo = "https://github.com/RattlesnakeOS/microg"

[[custom-prebuilts]]
modules = ["GmsCore","GsfProxy","FakeStore","com.google.android.maps.jar"]
repo = "https://github.com/RattlesnakeOS/microg"
```

A few points about the microG setup. Due to the way patches are applied in the stack, if you try to combine other patches, the build may fail. The combination of this with other patches hasn't been tested. The first time you boot, open the microG app and do the self-test. Give it the permissions and add location backends. If it still complains that network location is not enabled, you need to toggle the location from main android settings once for it to work. Ideally, you should get all check boxes after that. Finally, in Chromium, go to site settings, and disable the location permission for google.com; it causes crashes in the microG setup.

## Contributors
* https://github.com/pgera
