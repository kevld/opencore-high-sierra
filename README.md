# opencore-high-sierra
My opencore config for MacOS High Sierra

<h1>Specs</h1>
<h2>Hardware</h2> 
Motherboard : Gigabyte z490 Gaming X - https://www.gigabyte.com/fr/Motherboard/Z490-GAMING-X-rev-10#kf
CPU : Intel i5 10600K - https://www.intel.fr/content/www/fr/fr/products/sku/199311/intel-core-i510600k-processor-12m-cache-up-to-4-80-ghz/specifications.html
GPU : Nvidia GeForce GTX 1060 6Go, with 2 screens - https://www.nvidia.com/fr-fr/geforce/10-series/


<h2>What works</h2>
System, audio, ethernet connection (did not try with wifi adapter), usb, graphics acceleration with the dGPU (the GTX1060), iServices, USB sound cards, USB MIDI keyboard

<h2>What does not work (for now)</h2>
iGPU (intel graphics), sleep mode.

<h2>Random issues</h2>
Sometimes the computer shutdowns (panic) at the beginning of the boot sequence, start it again and the problem disappears.
After a work session on windows, then restarting on MacOS, sometimes my second screen turns off (with a "signal not found" message from the screen). Unplug and replug the cable fix this issue.

<h1>Before copying the files to the USB</h1>
Use GenSMBIOS to generate system UUID, and set it in the config.plist file.
Use iMac18,3 config (iMac20,2 as recommended for comet lake is not working for High Sierra)
More information on this page https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#platforminfo

Keep an eye on the open core docs available here : https://dortania.github.io/OpenCore-Install-Guide/

<h1>After installing</h1>
<h2>Post install main steps</h2>
Follow this guide https://dortania.github.io/OpenCore-Post-Install/ to make audio and iService working, then booting without usb.

<h2>Making the dGPU working</h2>
Steps : 
* Click the Apple menu, then about this Mac
* Click on the version number to show build number
* Check on this page if a driver is available with the High Sierra build number - https://www.tonymacx86.com/nvidia-drivers/
	* If yes, download it, and install it
	* If no, open terminal and copy/paste this (hanks to him for the script) : 
		* bash <(curl -s https://raw.githubusercontent.com/Benjamin-Dobell/nvidia-update/master/nvidia-update.sh)
	* Restart
* Enjoy :)
