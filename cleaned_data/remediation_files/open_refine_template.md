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

<titleInfo>
<title>Great Smoky Mountains Colloquy</title></titleInfo>

<titleInfo type="alternative" displayLabel="Also known as">
<title>Colloquy</title>
</titleInfo>


<originInfo>
<dateCreated encoding="edtf" keyDate="yes" point="start">
{{cells.machine_date.value}}
</dateCreated></originInfo>

<abstract>
{{cells.abstract.value}}
</abstract>

<physicalDescription>
<extent unit=”pages”>4</extent>
 <form authority="aat" valueURI="http://vocab.getty.edu/aat/300026652">
newsletters</form>
<internetMediaType>application/pdf</internetMediaType>

</physicalDescription>

{{if(cells.public_note.value != "NULL", "<note>" + cells.public_note.value + "</note>", "")}}

<location>
<physicalLocation>University of Tennessee Knoxville. Special Collections. 
</physicalLocation>
</location>

<language>
<languageTerm type="code" authority="iso639-2b">eng
</languageTerm>
</language>

<relatedItem displayLabel="Project" type="host"> 
<location><url>https://digital.lib.utk.edu/collections/colloquy
</url>
</location> 
<titleInfo>
<title>Great Smoky Mountains Colloquy</title></titleInfo>
</relatedItem>

<accessCondition type=”use and reproductions” xlink:href=”http://rightsstatements.org/vocab/InC/1.0/”>
In Copyright
</accessCondition>


{{ if (cells.name_2_name.value != "NULL",
"<name" +if(cells.name_2_uri.value != "NULL",
' authority="lcna" valueURI="'+cells.name_2_uri.value + '"', "") +
'><namePart>' + cells.name_2_name.value + '</namePart> ' +
if (cells.name_2_role.value != "NULL" , '<role> <roleTerm authority ="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/edt.html"> ' + cells.name_2_role.value + '</roleTerm> </role> ', "") + '</name>', "")}}

{{ if (cells.name_1_name.value != "NULL",
"<name" +if(cells.name_1_uri.value != "NULL",
' authority="lcna" valueURI="'+cells.name_1_uri.value + '"', "") +
'><namePart>' + cells.name_1_name.value + '</namePart> ' +
if (cells.name_1_role.value != "NULL" , '<role> <roleTerm authority ="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/edt.html"> ' + cells.name_1_role.value + '</roleTerm> </role> ', "") + '</name>', "")}}

{{ if (cells.name_3_name.value != "NULL",
"<name" +if(cells.name_3_uri.value != "NULL",
' authority="lcna" valueURI="'+cells.name_1_uri.value + '"', "") +
'><namePart>' + cells.name_3_name.value + '</namePart> ' +
if (cells.name_3_role.value != "NULL" , '<role> <roleTerm> ' + cells.name_3_role.value + '</roleTerm> </role> ', "") + '</name>', "")}}


{{ if(cells.subject_name_1_name.value != "NULL", "<subject><name " + if (cells.subject_name_1_name.value != "NULL", 'authority="lcna" valueURI="' + cells.subject_name_1_uri.value + '"', '') + "><namePart>" + cells.subject_name_1_name.value + '</namePart></name></subject>', '')}}

{{ if(cells.subject_topic_1_name.value != "NULL", "<subject><topic " + if(cells.subject_topic_1_uri.value != "NULL", 'authority="lcsh" valueURI="' + cells.subject_topic_1_uri.value + '"', '') + ">" + cells.subject_topic_1_name.value + "</topic></subject>", '')}}

</mods>

```

### Row Separator

**Leave Blank**

### Suffix

```
</modsCollection>
```