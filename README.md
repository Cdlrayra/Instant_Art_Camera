# Instant_Art_Camera
This is a self-designed instant art camera system based on the Raspberry Pi. The camera system is capable of taking photos, printing black-and-white images based on the captured pictures, and generating poetry based on the visual content of the shots. Additionally, a simple graphical user interface has been developed for the system.

## The workflow of the camera system
* The process framework diagram of the entire workflow：
* ![image](https://github.com/user-attachments/assets/0b095bfc-f16f-4013-9081-583b622c1b7e)
* The processing workflow diagram for generating poetry based on the captured image:
* ![image](https://github.com/user-attachments/assets/de79295d-256f-4186-ab24-1d49cfe0c4f9)
* The implementation code for this processing workflow is referenced from the repository
* (link:https://github.com/bokito-studio/poetry-camera-rpi).
* The processing workflow diagram for generating and printing a sketch of the captured image:
* ![image](https://github.com/user-attachments/assets/3841a91d-c109-45a3-8e42-7d3cd31a7976)
* This section employs the U2Net network to achieve the entire functions. Firstly, the U2Net network, loaded with weights trained for salient object detection, is used to detect salient objects in the scene, significantly improving the print quality of the thermal printer. Subsequently, the U2Net network, loaded with weights capable of generating sketches, is utilized for further processing of the scene, further enhancing the print quality. The comparison of print effects is illustrated in the following figure:
* ![image](https://github.com/user-attachments/assets/7605a5c2-6f14-4aaf-852b-34040ec8b694)

## Materials required to implement this project and the achieved results:

Hardware: Power bank, Raspberry Pi, connectable camera, thermal printer, button， and thermal paper.

Physical diagram of the implemented camera system：
* ![image](https://github.com/user-attachments/assets/0fafbcd0-c187-4226-905b-e425479842e0)
* ![image](https://github.com/user-attachments/assets/fe1d01b7-61f5-4104-ad08-7e255d0bcaae)
