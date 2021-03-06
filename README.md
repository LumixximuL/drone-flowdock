[![Build Status](https://cloud.drone.io/api/badges/jones2026/drone-flowdock/status.svg)](https://cloud.drone.io/jones2026/drone-flowdock)
[![](https://images.microbadger.com/badges/image/jones2026/drone-flowdock.svg)](https://microbadger.com/images/jones2026/drone-flowdock "Get your own image badge on microbadger.com")

# drone-flowdock
Drone plugin to push messages to Flowdock

#### Image name:
`jones2026/drone-flowdock`

#### Settings

| setting | required | description |
------------- | ------------- | ----------
flow_token | yes | Flowdock token for flow that message will be posted to
message | yes | message that will be posted to Flowdock
message_type | yes | specify [Flowdock MessageType](https://www.flowdock.com/api/message-types) currently supported types are: `message`, `activity`

#### Example usage

```
- name: flowdock
  image: jones2026/drone-flowdock
  settings:
      message: ":red_circle: failure on Drone :point_right: ${DRONE_BUILD_LINK}"
      flow_token:
          from_secret: FLOWDOCK_TOKEN
  when:
      status:
          - failure
```
