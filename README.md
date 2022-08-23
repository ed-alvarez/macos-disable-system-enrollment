# Disable macOS System Enrollment

Ever found a Macbook locked by this mechanism? Simply boot into recovery mode. Open up a shell, and run the following
commands in the same order:

> ⚠️** You must disable SIP first**

```
sudo mount -uw /

sudo mkdir /System/Library/LaunchAgentsDisabled

sudo mkdir /System/Library/LaunchDaemonsDisabled

sudo mv /System/Library/LaunchAgents/com.apple.ManagedClientAgent.agent.plist \
  /System/Library/LaunchAgentsDisabled

sudo mv /System/Library/LaunchAgents/com.apple.ManagedClientAgent.enrollagent.plist \
  /System/Library/LaunchAgentsDisabled

sudo mv /System/Library/LaunchDaemons/com.apple.ManagedClient.cloudconfigurationd.plist \
  /System/Library/LaunchDaemonsDisabled

sudo mv /System/Library/LaunchDaemons/com.apple.ManagedClient.enroll.plist \
  /System/Library/LaunchDaemonsDisabled

sudo mv /System/Library/LaunchDaemons/com.apple.ManagedClient.plist \
  /System/Library/LaunchDaemonsDisabled

sudo mv /System/Library/LaunchDaemons/com.apple.ManagedClient.startup.plist \
  /System/Library/LaunchDaemonsDisabled
```

Reboot your system and you should stop seeing the macOS system enrollment notification or any sort of alert related to it.
