# M5Stack-ESP-IDF_Getting_started
Commands for setting up ESP-IDF for the youtube video focusing on this subject

**install screen - serial terminal emulator**
sudo apt-get install screen

**install esp-idf dependencies**
sudo apt-get install git wget libncurses-dev flex bison gperf python python-pip python-setuptools python-serial python-click python-cryptography python-future python-pyparsing python-pyelftools cmake ninja-build ccache libffi-dev libssl-dev


**create esp directory, enter it and clone esp-idf git **
mkdir ~/esp/
cd ~/esp/
git clone https://github.com/espressif/esp-idf.git
cd esp-idf


**hash for esp-idf v3**
git checkout 9e70825d1e1cbf7988cf36981774300066580ea7
git submodule update --init --recursive

**xtensa toolchain install**
cd ~/esp/
wget https://dl.espressif.com/dl/xtensa-esp32-elf-linux64-1.22.0-80-g6c4433a-5.2.0.tar.gz

tar -xzf ~/Downloads/xtensa-esp32-elf-linux64-1.22.0-80-g6c4433a-5.2.0.tar.gz

**add paths to xtensa toolchain and esp-idf**
export PATH="$HOME/esp/xtensa-esp32-elf/bin:$PATH"
export IDF_PATH="$HOME/esp/esp-idf"

**clone m5stack esp-idf templates**
cd ~
git clone https://github.com/m5stack/M5Stack-IDF
cd ~
git clone https://github.com/m5stack/M5StickC-IDF

cd M5StickC_IDF
make menuconfig

**add user to dialout group/ allow access to com port**
Sudo usermod -a -G dialout $user
Sudo chmod a+rw /dev/ttyUSB0

make flash


