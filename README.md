# Navigation methods for InterSystems Objects Indexed properties

The project creates auto-generated methods for non-unique indices.

Creates the following methods:
- *IndexName*Open(val)
- *IndexName*First(val)
- *IndexName*Last(val)
- *IndexName*Next(val)
- *IndexName*Previous(val)

# Examples
- set person = ##class(samples.Person).NameIndexOpen("Daniel")
- SET person = person.NameIndexFirst("Daniel")
- SET person = person.NameIndexLast("Daniel")
- SET person = person.NameIndexNext("Daniel")
- SET person = person.NameIndexPrevious("Daniel")

```
set person = ##class(samples.Person).PhoneIndexOpen("880-555-4323")
While $IsObject(person) {
    write !, person.Name
    set person = person.PhoneIndexNext("880-555-4323")
}
```

# Install:

1. Import v*.*-export.xml in your project
2. Add to persistent classes Extends vassil2010.navMethodsForIndexedProperties.NavMethodsForIndexedProperties

Example: 
```
Class samples.Person Extends (%Persistent, vassil2010.navMethodsForIndexedProperties.NavMethodsForIndexedProperties, %Populate)
```

3. Compile the project
