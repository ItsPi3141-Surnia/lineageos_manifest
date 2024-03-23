# LineageOS 20 for Moto E 2015 (surnia)

- This is a WIP, don't expect it to work
  - It might never work
- This is for `surnia` only

To get started with Android, you'll need to get
familiar with [Git and Repo](https://source.android.com/source/using-repo.html).

1. Set up your environment
```bash
sudo apt-get install git-core
git clone https://github.com/akhilnarang/scripts
cd scripts
bash setup/android_build_env.sh
```

2. Then run these commands to get git all working:
```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

3. Then Create a folder for LineageOS and open it
```bash
mkdir los
cd los
```

4. To initialize your local repository using the LineageOS trees, use a command like this:
```bash
repo init -u https://github.com/ItsPi3141-Surnia/lineageos_manifest.git -b lineage-20.0 -g "default,-darwin" --depth=1 --git-lfs
```
> [!NOTE]
> If you're building on Darwin (MacOS), remove `-g "default,-darwin"`

5. Then to sync up:
```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```  

6. To start the build once everything is ready , Run to prepare our devices list
```bash
. build/envsetup.sh
```

7. Now build
```bash
brunch surnia  
```
