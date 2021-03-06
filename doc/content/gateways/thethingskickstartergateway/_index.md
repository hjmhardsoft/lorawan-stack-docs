---
title: "The Things Kickstarter Gateway"
description: ""
---

The Things Kickstarter Gateway is a LoRaWAN gateway, whose technical specifications can be found in [the official documentation](https://www.thethingsnetwork.org/docs/gateways/gateway/). This page guides you to connect it to {{% tts %}}.

## Prerequisites

1. User account on {{% tts %}} with rights to create Gateways and API Keys.
2. The Things Gateway running the latest firmware (a minimum of `v1.0.8` is necessary).

## Registration

Create a gateway by following the instructions for [Adding Gateways]({{< ref "/gateways/adding-gateways" >}}). Choose a **Gateway ID**. An **EUI** is not necessary.

Create an API Key with Gateway Link rights for this gateway using the same instructions. Copy the key and save it for later use.

## Configuration

Open the front panel of the gateway casing.

While the gateway is powered on, hold the pink reset button for 5 seconds (until each of the 5 LEDs illuminate). This erases the existing configuration on the gateway.

The gateway will now expose a WiFi Access Point whose SSID is of the form `TheThings-Gateway-xxxxx`, to which you should now connect using password `thethings`.

In a web browser, open the gateway's configuration page by navigating to http://192.168.84.1/

{{< figure src="ttkg-config-window.png" alt="TTKG Configuration Window" >}}

Enter the following fields:

1. **Name**: the **Gateway ID** that you chose earlier.
2. Choose the WiFi network from the drop down and enter a password if necessary.

> Note: To connect to a Cloud Hosted tenant, the tenant ID must be added to the  **Gateway ID** field in the format **Gateway ID**@**Tenant ID**.

Click the **Show Advanced Options** button and enter the following fields:

1. **Account Server**: The URL of {{% tts %}}. If you followed the [Getting Started guide]({{< ref "/getting-started" >}}) this is the same as what you use instead of `https://thethings.example.com`.
2. **Gateway Key**: The API Key that you created earlier.
3. Click **Save** when done.

This will apply the setting and reboot the gateway. If all the steps have been followed correctly, your gateway will now connect to {{% tts %}}.

## Troubleshooting

Please allow about 5 mins for the gateway to attempt connection before trouble shooting. During this period only 2 or 3 LEDs will be ON with the 3rd LED slowly blinking.

If there only 3 LEDs active for an extended period of time, unplug the gateway, wait for 10s and reconnect. Also try using an Ethernet connection as that improves the network connectivity.
