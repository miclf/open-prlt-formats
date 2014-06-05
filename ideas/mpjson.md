## Members of parliaments

This JSON structure takes a few good ideas by [Psycojoker](https://github.com/Psycojoker) from the [political-memory/django-representatives](https://github.com/political-memory/django-representatives/blob/master/format.json) repository.

```javascript
{
    "givenName": "John",
    "surname": "Doe",
    "gender": "M",
    "dateOfBirth": "1970-01-01",
    "dateOfDeath": null,
    "parties": [
        // Note: a MP could be in several parties at the same time (for example
        // at both national level and EU level)
        {
            // This is supposed to be a kind of ID
            // ISO 3166-1 alpha-2 + party abbreviation
            "id": "BE-ABC",
            "from": "1970-01-01",
            "to": "1970-01-01"
        },
        {
            "id": "BE-ABC",
            "from": "1970-01-01",
            "to": null
        }
    ],
    // General contact details, not linked to any mandate
    "contactDetails": {
        "addresses": [],
        "phones": [],
        "faxes": [],
        "websites": [],
        "socialNetworks": {}
    },
    "education": [
        // Array of strings
    ],
    "professionalCareer": [
        // Array of strings
    ],
    "publications": [
        // Array of strings
    ],
    "mandates": [
        {
            // This is supposed to be a kind of ID
            // ISO 3166-1 alpha-2 + assembly abbreviation
            "assemblyId": "BE-K",
            "from": "1970-01-01",
            "to": null,
            // We need to link a mandate to a party, in case a MP has several
            // mandates at the same time for different parties
            "party": "BE-ABC",
            // Constituency linked to the mandate. Should use a standard if
            // possible. ISO 3166-2:BE is used here as an example.
            "constituency": "BE-WLG",
            // Only contact details that are specifically linked to the current
            // mandate. More generic contact details or personal contact details
            // of the MP must not be referenced here.
            "contactDetails": {
                "addresses": [
                    {
                        // Type of address. Should come from a small list of
                        // possible values
                        "type": "office",
                        // Optional
                        "office": "Office 42",
                        // Optional
                        "floor": "3rd floor",
                        "number": "50-52",
                        "street": "Street Line 1\nStreet Line 2",
                        "postalCode": "12345",
                        "city": "City Name",
                        // ISO 3166-1 alpha-2
                        "country": "BE",
                        // Optional
                        "coordinates": {
                            // float number (16,14)
                            "latitude": 0,
                            // float number (17,14)
                            "longitude": 0
                        },
                        // Only for phone numbers associated to a physical
                        // location (in other words, not cell phones)
                        "phones": [
                            {
                                "number": "+32123456789",
                                // Optional
                                "comment": "Secretariat"
                            }
                        ],
                        // Same here, we expect faxes to be linked to places
                        "faxes": [
                            {
                                "number": "+32123456789",
                                // Optional
                                "comment": "Secretariat"
                            }
                        ]
                    }
                ],
                // Phone numbers should primarily be associated to locations. If
                // this is not possible (for example for cell phones), they can
                // be referenced here
                "phones": [
                    {
                        "number": "+32123456789",
                        // Optional
                        "comment": "Office"
                    }
                ],
                // Optional. Only for websites specifically linked to a given
                // mandate (should be rare). If a website is linked to the MP
                // but not to any specific mandate, it should be referenced
                // higher in the tree. URLs must be absolute.
                "websites": [
                    {
                        "url": "https://example.com",
                        // Optional
                        "comment": ""
                    }
                ],
                // Optional. Only if specifically linked to the current mandate.
                // URLs must be an absolute.
                "socialNetworks": {
                    "twitter": {
                        "url": "https://twitter.com/johndoe",
                        // Optional
                        "comment": ""
                    }
                }
            },
            // Participation of the MP to committes, working groups,
            // etc. during the mandate.
            "committees": [
                {
                    // This is supposed to be a kind of ID. This committee is
                    // itself related to a specific assembly
                    "committeeId": "INFRA",
                    "from": "1970-01-01",
                    "to": null,
                    "role": ""
                }
            ]
        }
    ],
    // Maybe find a better name… Array of events/mandates/whatever that are out
    // of the scope of this document (which is focusing on political mandates)
    // but that are still relevant to inform and provide context.
    "timeline": []
}
```

## Assemblies

```javascript
{
    // Chamber of Representatives
    "BE-K": {},
    // Senate
    "BE-S": {},
    // Walloon Parliament
    "BE-W": {},
    // Parliament of the French Community
    "BE-F": {},
    // Flemish Parliament
    "BE-V": {},
    // Brussels Parliament
    "BE-B": {},
    // Parliament of the German-speaking Community
    "BE-D": {}
}
```

JSON Schema: http://json-schema.org/documentation.html
