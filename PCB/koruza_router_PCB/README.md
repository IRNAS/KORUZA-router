# Koruza router layout

Layout for koruza router is done in [Altium designer][altium_link]. Also there is [PDF documentation][pdf_docs_link] of the project. 
The free version of the Altium designer viewer can be downloaded from this [link][altium_download].

### Mandatory:
* board shape
* board dimensions
* board mounting holes
* GPIO expansion connector position
* SFP modules must have separate cages
* components that must be on the front edge of the board:
  * reset button
  * status LEDs
  * USB 3.0 connector
  * 4x Ethernet RJ45 connectors
  * 2x SFP connectors, with separate cage, because one cage would net be soldered
  * DC jack 5V
  
  
### Not mandatory:
* microSD card slot can be placed on any edge, except front edge with connectors
* console header can be placed near any another edge
* 5.08mm 2-pin screw terminal can be placed on any edge, except front edge with connectors




![alt tag](https://github.com/IRNAS/KORUZA-router/blob/1G-router-requirements/PCB/koruza_router_PCB/pics/GPIO%20expansion%20connector%20pinout.png)


## Mechanical layout
![alt tag](https://github.com/IRNAS/KORUZA-router/blob/1G-router-requirements/PCB/koruza_router_PCB/pics/PCB_dimensions.png)

[altium_link]: http://www.altium.com/
[altium_download]: http://www.altium.com/altium-designer-viewer
[pdf_docs_link]: https://github.com/IRNAS/KORUZA-router/blob/1G-router-requirements/PCB/koruza_router_PCB/Project%20Outputs%20for%20koruza_router_PCB/koruza_router.PDF
