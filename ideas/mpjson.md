```json
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
    "mandates": [
        {
            // This is supposed to be a kind of ID
            // ISO 3166-1 alpha-2 + assembly abbreviation
            "assemblyId": "BE-K",
            "from": "1970-01-01",
            "to": null,
            "contactDetails": {
                "address": [
                    {
                        // Type of address. Should come from a small list of
                        // possible values
                        "type": "office",
                        "number": "50-52",
                        "street": "Street Line 1\nStreet Line 2",
                        "postalCode": "12345",
                        "city": "City Name",
                        // ISO 3166-1 alpha-2
                        "country": "BE",
                    }
                ],
                "phone": {
                    "office": "+32123456789"
                },
                "fax": {
                    "office": "+32123456789"
                },
                // extract to root? Single item instead of array?
                "website": [],
                // extract this to root?
                "socialNetworks": []
            }
        }
    ],
    // Maybe find a better name… Array of events/mandates/whatever that are out
    // of the scope of this document (which is focusing on political mandates)
    // but that are still relevant to inform and provide context.
    "timeline": []
}
```

JSON Schema: http://json-schema.org/documentation.html
