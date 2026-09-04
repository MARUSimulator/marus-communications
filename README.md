To install **MARUS2 Communications** and its required core dependencies, add them directly to your Unity project's **`Packages/manifest.json`** file under the `"dependencies"` block:

```json
{
  "dependencies": {
    "com.marus2.proto": "https://github.com/MARUSimulator/marus2-proto.git#csharp",
    "com.marus2.core": "https://github.com/MARUSimulator/marus2-core.git",
    "com.marus2.communications": "https://github.com/MARUSimulator/marus-communications.git"
  }
}
```

# Communications usage

This package provides communication and ranging device simulations for marine robotics in Unity, supporting underwater acoustic modems as well as terrestrial radio frequency (RF) devices.

To connect communication devices to external networks (such as ROS or remote tools), use the corresponding gRPC adapter scripts from the `marus-communications-grpc` module.

## Nanomodem

Simulates an underwater acoustic modem (such as the Blueprint Subsea SeaTrac / Nanomodem). It handles bidirectional acoustic message transmission, payload serialization, supply voltage simulation, and acoustic time-of-flight ranging with configurable measurement increment and variance.

## Acoustic Medium

Simulates sound propagation through an underwater acoustic channel. It calculates propagation delays based on distance and sound speed in water, models transmission loss and attenuation, and delivers messages to listening acoustic devices within communication range.

## LoRa Device

Simulates a LoRa (Long Range) RF transceiver. Supports packet-based RF messaging with configurable transmit power, carrier frequency, bandwidth, data rate, and line-of-sight range.

## LoRa Ranging

Calculates two-way time-of-flight ranging between a master LoRa device and one or more target LoRa nodes. Supports packet drop rate modeling (`PacketDropRate`) and produces timestamped range readings for localization and relative positioning algorithms.

## RF Medium

Simulates radio frequency signal propagation in air. Models transmission range and line-of-sight signal delivery between simulated RF transceivers.

## LoRa Dummy Transmitter

A utility component that periodically broadcasts sample LoRa packets at a configurable interval for testing network connectivity and receiver pipelines.