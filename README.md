# Tutorial Install OS Jetson Nano
## Step 1. Menginstall OS Jetson Nano, Ikuti panduan pada link dibawah ini
[STEP 1] (https://yunusmuhammad007.medium.com/1-getting-started-with-jetson-nano-developer-kit-a745c9cc598e)

## Step 2. Setup VNC Jetson Nano, Ikuti panduan pada link dibawah ini
[STEP 2] (https://yunusmuhammad007.medium.com/4-setup-vnc-server-pada-jetson-nano-35d3b6121234 (NOTE: Hanya Nomor 1 dan 3 ))

## Step 3. Uninstall Software yang tidak diperlukan
[STEP 3] (Source: https://yunusmuhammad007.medium.com/5-jetson-nano-minimal-os-c50fd1a4ffcd)
### Uninstall Thunderbird dan LibreOffice dan mengatasi error l4t_bootloader
1. Uninstall Software
```
sudo apt-get remove --purge thunderbird*
sudo apt-get remove --purge libreoffice*
sudo apt-get clean
sudo apt-get autoremove
sudo apt-get update
sudo apt-get upgrade
```
2. Fixing error l4t_bootloader
### Apparently it is related to the information that dpkg saves and it conflicts in the installation
So wee needed move /var/lib/info/ and create new /var/lib/dpkg/info
```
sudo mv /var/lib/dpkg/info/ /var/lib/dpkg/backup/
sudo mkdir /var/lib/dpkg/info/
```
### Next update repos and force install .
```
sudo apt-get update
sudo apt-get -f install
```
### Move the new structure dpkg/info to old info
```
sudo mv /var/lib/dpkg/info/* /var/lib/dpkg/backup/
```
### Remove the new dpkg structure folder and back the old
```
sudo rm -rf /var/lib/dpkg/info
sudo mv /var/lib/dpkg/backup/ /var/lib/dpkg/info/
sudo apt upgrade
```
### If this is not done, it will complain in the script and its installation will always fail

## Step 4. Install TensorFlow di Jetson Nano
[STEP 4] (source: https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html)
### Before you install TensorFlow for Jetson, ensure you:
1. Sebelum tahap install, kita perlu check JetPack version pada Jetson Nano yang kita gunakan, jalankan command berikut pada terminal
```
sudo apt-cache show nvidia-jetpack
```
2. Install System Package yang dibutuhkan Tensorflow
```
sudo apt-get update
sudo apt-get install libhdf5-serial-dev hdf5-tools libhdf5-dev zlib1g-dev zip libjpeg8-dev liblapack-dev libblas-dev gfortran
```
3. Install dan upgrade pip3
```
sudo apt-get install python3-pip
sudo -H pip3 install -U pip testresources setuptools==49.6.0 
```
4. Install depedency python yang dibutuhkan (proses membutuhkan waktu yang cukup lama)
```
sudo -H pip3 install -U --no-deps numpy==1.19.4 future==0.18.2 mock==3.0.5 keras_preprocessing==1.1.2 keras_applications==1.0.8 gast==0.4.0 protobuf pybind11 cython pkgconfig packaging scipy
sudo -H H5PY_SETUP_REQUIRES=0 pip3 install -U h5py==3.1.0
```
5. Install Tensorflow (proses membutuhkan waktu yang cukup lama)
```
sudo pip3 install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v45 tensorflow
```

## Step 5. Install Driver Razer Kiyo Pro di Jetson Nano, Ikuti panduan pada link dibawah ini
[STEP 5] (https://github.com/dimasalifta/install-driver-razer-kiyo-pro-jetson-nano)

## Step 6. Install package yang dibutuhkan game p9 dan m14 (proses membutuhkan waktu yang cukup lama)
[STEP 6] (Source:)
```
sudo apt-get install python3-tk python3-dev libcanberra-gtk-module
pip3 install nano matplotlib opencv-python opencv-contrib-python scikit-learn imutils keras==2.6 numpy==1.19.4 pyautogui
pip3 install --upgrade pandas

```
## Step 7. Cloning repository game
masuk ke directory Documents dulu baru cloning

```
git clone https://github.com/dimasalifta/game-m6.git
git clone https://github.com/dimasalifta/game-p9.git
```