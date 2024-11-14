# IOTC Python Lite Demo

This guide will help you set up and utilize the IoTConnect Python Lite SDK across a number of gateway devices to run a basic IoTConnect program that reports telemetry data in real-time to the IoTConnect cloud platform. 

## Step 1: Make an IoTConnect Account
* To get started making an IoTConnect account, you can contact our team at info@iotconnect.io

## Step 2: Sign in to IoTConnect Account
* An IoTConnect account is required to continue with this guide. If you need to create an account, a free 2-month subscription is available. Please follow the [Creating a New IoTConnect Account](https://github.com/avnet-iotconnect/avnet-iotconnect.github.io/blob/main/documentation/iotconnect/subscription/subscription.md) guide and return to this guide once complete.

## Step 3: Import a Template for Your Device 
* Within this git repo, navigate to the "common" directory and click on the file called pythondemo.JSON

* Download the template file to your PC by clicking on the download button for the individual file
  
* In IoTConnect, navigate to the "Devices" page and then select the “Templates” tab from the toolbar

* On the Templates page, click the “Create Template” button

* Click on the "Import" button

* In the resulting pop-up window, navigate to where you have the template file downloaded, and select the template file. Click on the "Save" button afterwards

## Step 4: Create a Your Device in IoTConnect
* Navigate back to the “Device” menu and click on “Create Device”

>[!IMPORTANT]
>For setup simplicity, this demo is designed for the Unique ID and the Display Name to be exactly the same, so it is critical that you make them identical to each other. It will not work otherwise.

* Enter the following information and then click “Save and View”:
   * Unique Id: <Your UniqueID/DisplayName Here>
   * Display Name: <Your UniqueID/DisplayName Here>
   * Entity: (Any Generic Entity Will Work)
   * Template: pythondemo

* In the resulting page, click “Connection Info”

* Click on the certificate icon in the resulting pop-up to download the zipped certificate package.

* Extract the certificate package folder and save the resulting certificates folder to a known location. You will relocate them later into the setup.

## Step 5: Customize Demo Configuration
* In another browser tab, navigate to [the top of this repository] (https://github.com/avnet-iotconnect/iotc-python-examples/tree/main) and download the repository's zip file 

* Unzip the downloaded folder and then open it
  
* Navigate to the *device-certificates* directory, located in the interior *iotc-python-lite-sdk* directory (the name of the overall repo and the first sub-directory will have the same name after extraction)

* Copy your two individual device certificates from the folder you saved in Step 4 into this folder.
  
>[!IMPORTANT]
>You cannot copy the whole certificate folder, you must copy the individual *.pem* and *.crt* files for the demo to function properly

* Back in the *iotc-python-lite-sdk* directory, open up the file *config.py* in a generic text editor.

* Copy your CPID and Environment into the *cpid* and *env* fields of *config.py*, **within the quotation marks.**

>[!TIP]
>To find your CPID and Environment, navigate to your main IoTConnect dashboard page, hover your cursor over the gear icon on the toolbar located on the far-left side of the page, and then click "Key Vault"

* Enter the Unique ID for your device from Step 4 into the *unique_id* field, **within the quotation marks.**

* Save the *config.py* file and close the text editor.

## Step 6: Configure Your Gateway

* Gateway configuration can vary slightly depending on your gateway model. Select the gateway-specific guide for your particular model and open it in another tab to complete this step before returning to Step 7.

## Step 7: Run the Demo and View the Data
* To run the demo, navigate to the *iotc-python-lite-sdk* directory on your gateway and then execute this command:
   ```python3 iotc-demo.py```

* In the IoTConnect webpage, navigate back to the “Device” menu and select your device's Unique ID from the list
  
>[!NOTE]
>You should see that the entry in the "Device Status" column shows a green "CONNECTED" label.

* Next, select "Live Data" from the toolbar on your device's page

* To get a more human-friendly report of the live telemetry data, click on the "Tabular" tab.
   * This tab allows you to scroll vertically to view previous data entires, and horizontally to see each individual attribute.

