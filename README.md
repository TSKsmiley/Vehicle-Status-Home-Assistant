# Car Door Status Visualization for Home Assistant

This custom visualization card for Home Assistant provides a real-time visual representation of your cars door, boot (trunk), and bonnet (hood) status, along with battery/fuel level and range information.

UPDATED: Now shows icons instead of labels, 


<img width="260" alt="Vehicle Status 2" src="https://github.com/user-attachments/assets/cdffc6d3-66dc-4c85-a9fe-24f4959c3653" />
<img width="257" alt="Vehicle Status 1" src="https://github.com/user-attachments/assets/8d1e082d-c96d-4ee9-bda3-70bd9418fa1a" />

This custom visualisation card for Home Assistant provides a real-time visual representation of your cars door, trunk, and hood status, along with battery/fuel level and range information.

I have included the files I used for the Volkswagen ID.4, add a new manual card and use the YAML in the included Vehicle-Status-Home-Assistant.yml file

## 📋 Description

This card uses the picture-elements feature in Home Assistant to provide a sleek, intuitive visualisation of your vehicles status. The card shows:

- A base image of your car when all doors are closed
- Visual door overlays that appear only when specific doors are open
- Current battery/fuel level
- Current range 
- Real-time updates as doors open and close

The visualisation leverages the state_filter property to dynamically show door overlays only when the corresponding doors are open, creating an intuitive and user-friendly representation of your vehicle's status.

## 🔧 Requirements

To use this card, you'll need:

1. Home Assistant with your cars integration set up
2. The binary sensors for your vehicle's doors, boot (trunk), and bonnet (hood)
3. Sensors for battery/fuel level and range
4. Images for your visualization (base car image and door overlays)

## 🖼️ Required Images

You'll need to provide the following images:

1. `default.jpg` - A top-down view of your your with all doors closed
2. `frontright.png` - Overlay showing the front right door open (transparent background)
3. `frontleft.png` - Overlay showing the front left door open (transparent background)
4. `backleft.png` - Overlay showing the left rear door open (transparent background)
5. `backright.png` - Overlay showing the right rear door open (transparent background)
6. `boot.png` - Overlay showing the trunk open (transparent background)
7. `boot.png` - Overlay showing the hood open (transparent background)

All overlay images should have transparent backgrounds except for the specific door, and should exactly match the dimensions of the base image.

## 🚗 Entity Configuration

The card expects that your car should be able to tell if a door is open or closed, the fuel/battery level, and the distance/range left

## 🔄 How It Works

The card works using the `state_filter` property in picture-elements to control image opacity based on sensor states:

- When a door is closed (sensor state is "on"), the overlay has 0% opacity (invisible)
- When a door is open (sensor state is "off"), the overlay has 100% opacity (fully visible)

This creates a seamless effect where door overlays only appear when the corresponding doors are actually open in your car.

## 🤝 Contribution

Feel free to fork this repo and make improvements! This is a community project to enhance the vehicle visualisation experience in Home Assistant.

## 📝 License

This project is released under the MIT License - feel free to use, modify, and distribute as needed.
