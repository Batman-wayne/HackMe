The official public repository for the HackMe project. Want to contribute? Contact Harris Mohamed (hmoham25@illinois.edu) or Amith Chivikula (amithc2@illinois.edu) 

Winner of the HackIllinois 2019 Ocean Source Software (presented by Particle), The Very Hungry Caterpillar (presented by Caterpillar), and Runners Up for the event overall.

This project is open source according to the GNU Affero General Public License v3.0. Check the license.txt for more details.

Before contributing to this project, please read the READMEs for software and hardware, depending on which one you want to contribute to. They contain setup information and will expedite the set-up process. 

# Project overview and description 
The HackMe project was conceived to bring a previously obscure field right into the consumer's hands: Electroencephalography (EEG waves). While normally used for diagnosing brain disorders (such as epilepsy and seizure-related disorders), there is actually a plethora of information to glean from these EEG waves. In general, everyone's brain will generate miniscule electrical impulses (extremely miniscule, on the order of 50microvolts). By finding the frequency of these waves, we can characterize a person's state. We can go further and apply even more advanced mathematics to figure out the location of these waves. 

The waves are measured from the brain by using non-invasive electrodes. These electrodes are cleverly hidden in our signature product, the HackMe beanie. This beanie, if further developed, would house a small custom PCB that does all the signal processing. 

After the waves are fully quantized, we can begin doing exciting things like mapping these waves to corresponding thoughts by using advanced learning algorithms and techniques. After enough mappings, thoughts can then be corresponded directly to thoughts through the use of embedded technology and the internet of things (IoT). For instance, if the user wants to turn up the thermostat, the action is complete as soon as the user thinks it because the wave will have been mapped to that action. 

The project is split up into several parts: The pre-processing side (Taking the signal from the brain all the way to quantizing it), processing (database side), post-processing (advanced analysis techniques on the wave), and the user integration (the website and the IoT interface).

In addition, our project aims to be one of the first offering truly open source, anonymous, very readable EEG-wave data for use in studies or any condition. We had great detail in finding resources to start 

# Pre-processing 
The fundamental problem with a wave as small as the electrical ones from the exterior of the brain is how miniscule they are. We began by coming up with a way to accurately read these waves. We used a 24 bit ADC (Analog-to-Digital converter) to accurately read the incoming waves. Once on a microcontroller, these waves can be stored and sent anywhere. For HackIllinois 2019, we had a Raspberry Pi 3 take these signals and upload them to a database. 

# Processing 
To host our data, we chose to use an Azure database as we get free access to it. The database can be written to and queried very easily, and separates all the data according to whether it is private patient data or part of the open source set. 

# Post-processing 
This is done through Matlab, using some of their built in models. After post processing is done, the type of wave which was encounted is pushed back to the server. Some of the most common EEG waves:
- Delta (3 Hz): Most commonly found in deep cycles of sleep. 
- Theta (3.5 to 7 Hz): Most commonly found in children. Implies an abnormality in the person if they are an adult.
- Alpha (7.5 to 13 Hz): Most commonly found in people who are relaxing and is eradicated by any deep concentration. 
- Beta: (14 > Hz): Most commonly found in people who are thinking a lot of thoughts at once.

The code is currently being ported over to Python.

# User integration 
Of course, the above 3 layers will not be even be seen by the user. The user only interacts through the product by wearing the HackMe beanie and accessing the website. There is a website (built in NativeScript + Angular), an app (support for both Windows and Android), and control of basic devices one might find in a home. 

# Next steps 
- PCB development: Developing circuitry to handle the signal processing and data upload. The smaller the board, the better. [Mark I currently in development]
- Post-processing algorithm development: Using machine learning algorithms, mass amounts of data, and advanced signal processing techniques, the goal here is to map raw waveforms to thoughts. [Matlab code being ported over to Python]
- Database programming: MongoDB research and development to replace the Azure implementation.
- Front End: Developing an aesthetic and slick interface (website + app) for the user to see their data, as well as adding more functionality. 
- IoT interface: Finding new and creative ways to apply mapped thoughts to the outside world. [Currently integrating Google Home into the HackMe interface]
