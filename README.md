# Accessible Address Autocomplete

Address autocomplete UI for PostCoder Web from Allies.

Designed to work well with screen readers and other assistive technologies.

## Basic usage

```
<link rel="stylesheet" href="allies-autocomplete.css">

<label for="allies_autocomplete">Enter a postcode or start typing an UK address</label>
<input id="allies_autocomplete" type="text">

<script src="allies-autocomplete.js"></script>
<script>
    var autocomplete_input = document.getElementById("allies_autocomplete");

    var allies_complete = new AlliesComplete(autocomplete_input, {
        apiKey: "PCW45-12345-12345-1234X",
        endpoint: "address",
        maxItems: 10
    });
    
    autocomplete_input.addEventListener("allies-complete-selectcomplete", function(e) {

        // Do something with the selected address here
        // Address fields found in the 'e.address' object

    });
</script>
```

## Options

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Default</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>apiKey</td>
            <td>PCW45-12345-12345-1234X</td>
            <td>
            This is an API key for a PostCoder Web accounts, available at - https://www.alliescomputing.com/postcoder/sign-up   
            Default is the a test key (Locked to addresses in the NR14 7PZ postcode)
            </td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td>address</td>
            <td>
            Endpoint to get final address data from when user selects an address from list   
            Also accepts 'addressgeo' which returns latitude and longitude along with full address
            </td>
        </tr>
        <tr>
            <td>addresslines</td>
            <td>2</td>
            <td>
            Number of address lines to split elements over, 1 - 10 accepted.   
            Returns 'addressline1', 'addressline2' etc  
            If address is short, blank fields will not be returned.
            </td>
        </tr>
        <tr>
            <td>excludeFields</td>
            <td>organisation</td>
            <td>
            Comma seperated list of fields to exclude from address lines output  
            More information can be found - https://developers.alliescomputing.com/postcoder-web-api/address-lookup/premise
            </td>
        </tr>
        <tr>
            <td>maxItems</td>
            <td>10</td>
            <td>
            Number of items to show in list below input box. Max 100.
            </td>
        </tr>
    </tbody>
</table>

### Credits

Heavily based on Awesomplete by Lea Verou http://leaverou.github.io/awesomplete  
Learning from the work GDS have done with their autocomplete https://designnotes.blog.gov.uk/2017/04/20/were-building-an-autocomplete/