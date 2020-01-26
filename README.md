# Set State
Home Assistant Python Script to force set an entity state

## How it works
This script adds a service that lets you update the state and/or attributes of any entity, similar to the developer tools

Requires `python_script:` to be enabled in you configuration

## Installation

### HACS
Requirements:
 - HACS version 0.9 or higher
 - Enabled `python_scripts:` in your Home Assistant configuration
 - Enabled `python_scripts` as option, in the HACS configuration. (If you missed this, kindly read below!)
 
You are only able to use this custom repo with HACS, if Python Scripts is enabled in Home Assistant. Also, "python_scripts" should have been enabled during the HACS setup through "Integrations" in Home Assistant.
![Missing Python as option](https://i.imgur.com/IGA4LVz.png)

If you missed that part, you need to remove HACS, and add it again, in order to find the "Python Script" category! This time, remember to set a checkmark in "Enable python_scripts discovery & tracking":

![HACS Configuration](https://i.imgur.com/bjDUwDz.png)

Find more information about the HACS configuration [here](https://hacs.xyz/docs/configuration/basic#changing-the-configuration) and [here](https://hacs.xyz/docs/categories/python_scripts). _If you used the YAML-way to configure HACS, it's a bit easier. Just edit the YAML configuration for HACS. That parts is also mentioned [https://hacs.xyz/docs/categories/python_scripts#enable-if-you-used-yaml-to-configure-hacs](here)._

![All good](https://i.imgur.com/odPV98j.png)

### Manual ###
Copy the Python script in to your `/config/python_scripts` directory.

## Service arguments
key | required | type | description
-- | -- | -- | --
`entity_id:` | True | string | The full entity id to update
`state:` | False | any | The state value
`allow_create:` | False | Boolean | Allow the entity to be created if it does not exists (Defaults to false so mis-typed entities do not                                       accidentally get created.)
`...:` | False | any | any additional name becomes or replaces and attribute on the entity

## Usage
Each call requires at least an entity_id and a state or attributes (otherwise it wont do anything)

example:

```
entity_id: sensor.random_sensor
state: 0
allow_create: true
```

(Thanks to [@rodpayne](https://community.home-assistant.io/u/rodpayne) for the initial script:
(https://community.home-assistant.io/t/how-to-manually-set-state-value-of-sensor/43975)
