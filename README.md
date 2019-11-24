# Set State
Home Assistant Python Script to force set an entity state

## How it works
This script adds a service that lets you update the state and/or attributes of any entity, similar to the developer tools

Requires `python_script:` to be enabled in you configuration

## Installation

### HACS ###
To install this with HACS you must add this repository as a Python Script, as this code is a service via python script and not a custom component.

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
