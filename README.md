# homebridge-liftmaster2 (Deprecated)
LiftMaster Plugin for [HomeBridge](https://github.com/nfarina/homebridge) (API 2.0)

Older verion using API 1.0: [homebridge-liftmaster](https://github.com/nfarina/homebridge-liftmaster)

# Installation
1. Install homebridge using `npm install -g homebridge`.
2. Install this plugin using `npm install -g git+https://github.com/luisiam/homebridge-liftmaster2.git`.
3. Update your configuration file. See configuration sample below.

# Removal
1. Stop homebridge.
2. Remove configuration in `config.json`.
3. Start homebridge (the plugin will remove cached accessories automatically).
4. Remove this plugin using `npm remove -g homebridge-liftmaster2`.
5. Restart homebridge.

# Configuration
Edit your `config.json` accordingly. Configuration sample:
 ```
"platforms": [{
    "platform": "LiftMaster2",
    "username": "email@email.com",
    "password": "password"
}]
```

### Advanced Configuration (Optional)
This step is not required. HomeBridge with API 2.0 can handle configurations in the HomeKit app.
```
"platforms": [{
    "platform": "LiftMaster2",
    "name": "MyQ",
    "username": "email@email.com",
    "password": "password",
    "openDuration": 15,
    "closeDuration": 25,
    "polling": true,
    "longPoll": 300,
    "shortPoll": 5,
    "shortPollDuration": 120,
    "gateways": ["My Home"]
}]

```

| Fields            | Description                                      | Default | Required |
|-------------------|--------------------------------------------------|---------|----------|
| platform          | Must always be `LiftMaster2`.                    |         | Yes      |
| name              | For logging purposes.                            |         | No       |
| username          | Your MyQ account email.                          |         | Yes      |
| password          | Your MyQ account password.                       |         | Yes      |
| openDuration      | Time in `s` to open garage door completely.      | 15      | No       |
| closeDuration     | Time in `s` to close garage door completely.     | 25      | No       |
| polling           | State polling.                                   | false   | No       |
| longPoll          | Normal polling interval in `s`.                  | 300     | No       |
| shortPoll         | Polling interval in `s` when door state changes. | 5       | No       |
| shortPollDuration | Duration in `s` to use `shortPoll`.              | 120     | No       |
| gateways          | Array of gateway IDs or names to add.             | []      | No       |
