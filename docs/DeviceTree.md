Objective

Understand how Zephyr separates hardware description from application code.



************************************************************************************************************************************************************************************************

Motivation

Instead of hardcoding:
#define LED_PIN 2

Zephyr describes hardware using Devicetree.

Application code remains portable across boards.

************************************************************************************************************************************************************************************************
Board Devicetree

For ESP32 DevKitC: boards/espressif/esp32_devkitc/
Contains: esp32_devkitc_procpu.dts

************************************************************************************************************************************************************************************************
Overlay

Application-specific hardware additions.

Example:
/ {
    aliases {
        led0 = &user_led;
    };

    leds {
        compatible = "gpio-leds";

        user_led: led_0 {
            gpios = <&gpio0 2 GPIO_ACTIVE_HIGH>;
        };
    };
};

Alias
aliases {
    led0 = &user_led;
};
Creates a logical name: led0 which is used by application. 
