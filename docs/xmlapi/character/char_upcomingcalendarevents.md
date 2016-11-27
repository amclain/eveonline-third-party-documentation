# UpcomingCalendarEvents
Retrieve character upcoming calendar events.

* __Path:__ ``/char/UpcomingCalendarEvents.xml.aspx``
* __Cache timer:__ 60 minutes
* __Access mask:__ 1048576
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
                <td>Character ID for which upcoming calendar events will be requested</td>
            </tr>
        </tbody>
    </table>

```xml
<result>
    <rowset name="upcomingEvents" key="eventID" columns="eventID,ownerID,ownerName,eventDate,eventTitle,duration,importance,response,eventText,ownerTypeID">
        <row eventID="93264" ownerID="1" ownerName="" eventDate="2011-03-26 09:00:00" eventTitle="EVE Online Fanfest 2011" 
duration="0" importance="0" response="Undecided" eventText="Join us for &lt;a href=&quot;http://fanfest.eveonline.com/&quot;&gt;
EVE Online's Fanfest 2011&lt;/a&gt;!" ownerTypeID="0" />
    </rowset>
</result>
```

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>upcomingEvents</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing 1 row per upcoming event.</td>
        </tr>
        <tr>
            <td></td>
            <td>eventID</td>
            <td><strong>long</strong></td>
            <td>Unique ID of event.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerID</td>
            <td><strong>long</strong></td>
            <td>ID of the character, corporation or alliance that created and owns the event.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerName</td>
            <td><strong>string</strong></td>
            <td>Name of character, corporation or alliance that created the event.  This field is blank when ownerID is 1 (CCP).</td>
        </tr>
        <tr>
            <td></td>
            <td>eventDate</td>
            <td><strong>datetime</strong></td>
            <td>Date and time event will start.</td>
        </tr>
        <tr>
            <td></td>
            <td>eventTitle</td>
            <td><strong>string</strong></td>
            <td>Event title.</td>
        </tr>
        <tr>
            <td></td>
            <td>duration</td>
            <td><strong>int</strong></td>
            <td>Duration of the event in minutes.  Minimum value is 0.  Maximum value is 1440.</td>
        </tr>
        <tr>
            <td></td>
            <td>importance</td>
            <td><strong>boolean</strong></td>
            <td>1 (TRUE) if the event is marked "important".  0 (FALSE) otherwise.</td>
        </tr>
        <tr>
            <td></td>
            <td>response</td>
            <td><strong>string</strong></td>
            <td>Character's response to event invitation.  One of "Undecided", "Accepted", "Declined" or "Tentative".</td>
        </tr>
        <tr>
            <td></td>
            <td>eventText</td>
            <td><strong>string</strong></td>
            <td>Event description.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerTypeID</td>
            <td><strong>long</strong></td>
            <td>Type ID of the event owner.</td>
        </tr>
    </tbody>
</table>
