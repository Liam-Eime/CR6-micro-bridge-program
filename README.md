# CR6-micro-bridge-program
Repository for my work with a Campbell Scientific CR6 data logger with LoggerNet, for a micro-bridge logging and demonstration kit.

# This program is designed for a micro-bridge demonstration project. It is designed to collect data from the following sensors and for the following purposes:

## 5 foil strain gauges, each forming a quarter of a full-bridge. The strain is measured using 4WFBS350 full-bridge terminal input modules.

### Strain gauges 1-4 are placed symmetrically on the 4 pillars of the micro-bridge, and are used like a mass/weight reading to determine the centre of mass/load of the bridge.

### Strain gauge 5 is placed on the underside of the bridge as a way to convert the strain to a mass/weight with calibration.

## 1 tri-axis accelerometer, reading only the z-axis currently due to availability of universal terminals on the CR6.

### Accelerometer is used to measure bridge vibrations.

## 1 Tfmini Plus LiDAR sensor. It uses the UART serial and digital communication protocol.

### LiDAR is used to measure the distance from the ground up to the underside of the bridge, to measure bridge deflections.

# This project does come with the following issues:

## The LiDAR sensor is limited by its resolution of only 1cm.

## The centre of mass result is certainly not accurate. With the current bridge and set-up, the changes in strain for the 4 pillar strain gauges is too insensitive to loading the bridge.

### These gauges also appear to read/produce quite a bit of noise which destabilises the result of determining the centre, especially after zeroing the strain.

### The sensitivity to noise is somewhat combated by taking the average reading of the strain over some less frequent interval than the scan rate.

### The averaging involves a trade-off between response time and sensitivity to noise:

#### The slower the scan rate the less sentitive the calculation of the centre is to noise, but the response time to update the centre is decreased.

## Similar noise issue are present with the mass/weight strain reading, resulting in an unstable value.
