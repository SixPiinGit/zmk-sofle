# zmk-config-sofle


<img src="keymap-drawer/sofle.svg" >

# 本地编译

```bash
cd zmk-sofle
mkdir modules;cd modules
git clone https://github.com/GPeye/hammerbeam-slideshow.git

python3 -m venv .venv
source .venv/bin/activate
cd ./app

#left_studio
west build -p -d ../zmk-sofle/build/left_studio -b sofle_left -S studio-rpc-usb-uart -- -DSHIELD=nice_view \
-DCONFIG_ZMK_STUDIO=y -DCONFIG_ZMK_STUDIO_LOCKING=n -DZMK_EXTRA_MODULES="../zmk-sofle"


#right
west build -p -d ../zmk-sofle/build/right -b sofle_right -- -DSHIELD=nice_view_custom \
-DZMK_EXTRA_MODULES="../zmk-sofle;../zmk-sofle/modules/hammerbeam-slideshow"
```