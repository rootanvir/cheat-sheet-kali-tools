
# bluetoothctl Command Cheatsheet

## Basic Commands

1. **Start the Bluetooth control interface**
   ```bash
   bluetoothctl
   ```

2. **Power on the Bluetooth controller**
   ```bash
   power on
   ```

3. **Power off the Bluetooth controller**
   ```bash
   power off
   ```

4. **Show the status of the Bluetooth controller**
   ```bash
   show
   ```

5. **Exit `bluetoothctl`**
   ```bash
   exit
   ```

---

## Device Management

1. **List paired devices**
   ```bash
   paired-devices
   ```

2. **List connected devices**
   ```bash
   devices
   ```

3. **Show the details of a specific device**
   ```bash
   info <device_mac_address>
   ```
   Example:
   ```bash
   info 00:1A:7D:DA:71:13
   ```

4. **Remove a paired device**
   ```bash
   remove <device_mac_address>
   ```
   Example:
   ```bash
   remove 00:1A:7D:DA:71:13
   ```

5. **Disconnect a device**
   ```bash
   disconnect <device_mac_address>
   ```

6. **Pair with a device**
   ```bash
   pair <device_mac_address>
   ```
   Example:
   ```bash
   pair 00:1A:7D:DA:71:13
   ```

7. **Trust a device (automatically connect in the future)**
   ```bash
   trust <device_mac_address>
   ```

8. **Untrust a device**
   ```bash
   untrust <device_mac_address>
   ```

9. **Connect to a device**
   ```bash
   connect <device_mac_address>
   ```

10. **Disconnect from a device**
    ```bash
    disconnect <device_mac_address>
    ```

11. **Display the list of devices discovered**
    ```bash
    devices
    ```

---

## Discovery and Scanning

1. **Start scanning for devices**
   ```bash
   scan on
   ```

2. **Stop scanning for devices**
   ```bash
   scan off
   ```

3. **Enable the agent (for pairing and authorization)**
   ```bash
   agent on
   ```

4. **Set the agent to be able to handle authentication and pairing**
   ```bash
   agent NoInputNoOutput
   ```

5. **Start advertising the device**
   ```bash
   advertise on
   ```

6. **Stop advertising the device**
   ```bash
   advertise off
   ```

---

## Controller Management

1. **List available Bluetooth controllers**
   ```bash
   list
   ```

2. **Select a specific Bluetooth controller**
   ```bash
   select <controller_mac_address>
   ```

3. **Set the Bluetooth controller to be discoverable**
   ```bash
   discoverable on
   ```

4. **Set the Bluetooth controller to be non-discoverable**
   ```bash
   discoverable off
   ```

5. **Make the Bluetooth controller pairable (accept incoming pairing requests)**
   ```bash
   pairable on
   ```

6. **Set the Bluetooth controller to be non-pairable**
   ```bash
   pairable off
   ```

7. **Set the Bluetooth controller to be trusted**
   ```bash
   trusted on
   ```

8. **Set the Bluetooth controller to be non-trusted**
   ```bash
   trusted off
   ```

---

## Audio / A2DP / AVRCP Control

1. **List available audio devices**
   ```bash
   list audio
   ```

2. **Connect to an audio device (A2DP)**
   ```bash
   connect <device_mac_address>
   ```

3. **Disconnect from an audio device (A2DP)**
   ```bash
   disconnect <device_mac_address>
   ```

---

## Advanced Options

1. **Set the controller to be in Low Energy (LE) mode**
   ```bash
   le on
   ```

2. **Set the controller to be in Classic Bluetooth mode**
   ```bash
   classic on
   ```

3. **Set the controller to be in Dual mode (both Classic and LE)**
   ```bash
   dual on
   ```

4. **Enable or disable Bluetooth power saving mode**
   ```bash
   power save on
   power save off
   ```

---

## Helpful Status and Debugging Commands

1. **Get help for all commands**
   ```bash
   help
   ```

2. **Display the current Bluetooth controller's information**
   ```bash
   show
   ```

3. **Check the Bluetooth agent status**
   ```bash
   agent
   ```

4. **Show the current paired and connected devices**
   ```bash
   devices
   ```

---

## Example Workflow:
1. Start `bluetoothctl`:
   ```bash
   bluetoothctl
   ```

2. Power on the Bluetooth controller:
   ```bash
   power on
   ```

3. Start scanning for nearby devices:
   ```bash
   scan on
   ```

4. Trust and pair with a device:
   ```bash
   trust <device_mac_address>
   pair <device_mac_address>
   ```

5. Connect to the paired device:
   ```bash
   connect <device_mac_address>
   ```

6. Disconnect from the device:
   ```bash
   disconnect <device_mac_address>
   ```

7. Exit `bluetoothctl`:
   ```bash
   exit
   ```

