# Colloquy Open Refine Template

### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

### Row Template

```

<mods xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
<identifier type="local">{{cells.identifier.value}}</identifier>
<titleInfo><title>Great Smoky Mountains Colloquy</title></titleInfo>
<titleInfo type="alternative" displayLabel="Also known as">
<title>Colloquy</title>
{{ if(cells.name_1_name.value != "NULL", '<name type="personal"' + if(cells.name_1_uri.value != "NULL", ' authority="lcnaf" valueURI="' + cells.name_1_uri.value + '"', '') + '><namePart>' + cells.name_1_name.value + '</namePart></name>', '')}}
</titleInfo>


</mods>

```

### Row Separator

**Leave Blank**

### Suffix

```
</modsCollection>
```