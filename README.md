## Preview

![Alt text](https://i.imgur.com/XcSn8jM.jpg)

## Permissions

This plugin uses the permission system. To assign a permission, use `oxide.grant <user or group> <name or steam id> <permission>`. To remove a permission, use `oxide.revoke <user or group> <name or steam id> <permission>`.

 - `markermanager.use` -- Allows player to use the /marker chat commands

 ## Chat Commands
- `/marker add name(code name) duration(seconds, 0 to permanent) refreshRate(30) radius(0.4) displayName(on map) colorInline(HEX) colorOutline(HEX) alpha(1) vendingonoff(true)` - add marker on map

- `/marker remove name (code name, only for custom markers)` - remove marker from map

#### Examples

- `/marker add test1 0 3 0.4 "Test Marker" 00ffff 00ffff 1 true`

- `/marker remove test1`
 
## Developer API

#### Adding markers on positions

```cs 
private void CreateMarker(Vector3 position, string name, int duration = 0, float refreshRate = 3f,float radius = 0.4f, string displayName = "Marker", string colorMarker = "00FFFF", string colorOutline = "00FFFFFF", float alpha = 1f, bool named = true)
{
    Interface.CallHook("API_CreateMarker", position, name,duration, refreshRate, radius, displayName, colorMarker, colorOutline, alpha, named);
} 
```

#### Adding markers attached to entities

```cs
private void CreateMarker(BaseEntity entity, string name, int duration = 0, float refreshRate = 3f,float radius = 0.4f, string displayName = "Marker", string colorMarker = "00FFFF", string colorOutline = "00FFFFFF", float alpha = 1f, bool named = true)
{
     Interface.CallHook("API_CreateMarker", entity, name,duration, refreshRate, radius, displayName, colorMarker, colorOutline, alpha, named);
} 
```

#### Removing marker by name

```cs
private void RemoveMarker(string name)
{
    Interface.CallHook("API_RemoveMarker", name);
} 
```
 
## Credits
 
- Shinnova, the original author of this plugin
- Orange, for helping maintain the plugin
- RocketMyrr, Continuing maintaining the plugin
