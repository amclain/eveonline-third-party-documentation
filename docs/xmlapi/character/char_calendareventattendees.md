# CalendarEventAttendees
Returns a list of all invited attendees for a given event.

* __Path:__ ``/char/CalendarEventAttendees.xml.aspx``
* __Cache timer:__ 10 minutes
* __Access mask:__ 4
* __Parameters:__
    <table border="1">
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
            <tr>
                <td>characterID</td>
                <td><strong>long</strong></td>
                <td>ID of character</td>
            </tr>
            <tr>
                <td>eventIDs</td>
                <td><strong>long</strong></td>
                <td>IDs of the events</td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<result>
    <rowset name="eventAttendees" key="characterID" columns="eventID,characterID,characterName,response">
        <row eventID="1451448" characterID="123456789" characterName="Jane Doe" response="Accepted" />
        <row eventID="1451449" characterID="987654321" characterName="John Doe" response="Tentative" />
        <row eventID="1451450" characterID="192837645" characterName="Another Doe" response="Declined" />
        <row eventID="1451451" characterID="918273465" characterName="Doe the Third" response="Undecided" />
    </rowset>
</result>
```

### Result Data

<table border="1">
    <tbody>
        <tr>
            <th>Name</th>
            <th>Data type</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>eventID</td>
            <td>long</td>
            <td>ID of the event.</td>
        </tr>
        <tr>
            <td>characterID</td>
            <td>long</td>
            <td>ID of the character.</td>
        </tr>
        <tr>
            <td>characterName</td>
            <td>string</td>
            <td>Name of the character.</td>
        </tr>
        <tr>
            <td>response</td>
            <td>string</td>
            <td>Can be {"Undecided", "Accepted", "Declined" or "Tentative"}</td>
        </tr>
    </tbody>
</table>

### Notes

* A call to <a href="char_upcomingcalendarevents.html">Character - UpcomingCalendarEvents</a> must be made prior to calling this API. Otherwise you will receive the error:<br />
    216: Calendar Event List not populated with upcoming events. You cannot request any random eventID.

### References

[Tyrannis API Improvements](http://community.eveonline.com/news/dev-blogs/tyrannis-api-improvements/)
