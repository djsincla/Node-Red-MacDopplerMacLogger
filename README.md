# Node-Red Activities

Working with Node-Red to Monitor/automate some amateur radio activities. Specifically MacLogger/MacDoppler spot reports which can be use for status and automation associated with satellite tracking.

## Dependencies
In your Node-Red Pallette screen: 
- Search of aedes to find the aedes mqtt broker node I am using. If you already have a broker, this is not needed.
- Search for tcp-client to find the tcp-client node. I'm not using it yet but plan to.
- Search for simple-queue. I use this to manage messaging and flow.
- Search for desktop. I use this for ui objects.

## Flows are self contained but there are two required Flows:
1. Aedes MQTT Broker.json: A message broker and the Flow Aedes MQTT Broker is provided if you are not already using a MQTT broker.
2. MacLogger MacDoppler Reports.json: Takes received reports from MacDoppler and MacLogger and throws them on the MQTT message queue.

## The following flows leverage the above MQTT messages:

1. MacLogger DX Spots UI.json: A simple tab which lists DX spots identified by WSJT-X
2. Gemini HF-1K.json and Gemini HF-1K UI.json monitor the status of the Gemini HF-1K amp. No automation yet and minimal UI as this is work in progress.
3. iOptron IO.json: Communucation to an iOptron AZ Mount Pro Telescope Mount via TCP/IP.
4. iOptron UI.json: Status display and control of Telescope Mount.
5. iOptron Auto.json: Automation between MacDoppler Rotor Reports and iOptron Telescope Mounts.


