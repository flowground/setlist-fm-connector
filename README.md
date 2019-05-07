# ![LOGO](logo.png) setlist.fm **flow**ground Connector

## Description

A generated **flow**ground connector for the setlist.fm API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/setlist.fm/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:01+03:00

## API Description

<p>
The setlist.fm API has been designed to give you easy access to setlist data in order to build fancy websites and
other applications. Before starting to use the API, be sure to ...
<ol>
<li>... understand how setlist.fm works (the <a href="https://www.setlist.fm/faq">FAQ</a> and the
<a href="https://www.setlist.fm/guidelines">Guidelines</a> are a good starting point),</li>
<li>... read this documentation carefully and</li>
<li>... <a href="https://www.setlist.fm/settings/api">apply for an API key</a> (link for logged in users only) - if
you're no registered user yet, then <a href="https://www.setlist.fm/signup">register first</a> (it's free).</li>
</ol>
</p>
<p>
If this documentation isn't enough or if you've got other things you'd like to tell us about the API, visit the
<a href="https://www.setlist.fm/forum/setlistfm/setlistfm-api">API Forum</a>.
</p>
<p>
Note that the setlist.fm API is, according to the <a href="https://www.setlist.fm/help/api-terms">API terms of
service</a>, only free for non-commercial projects. If you're interested in using the API for commercial purposes,
<a href="https://www.setlist.fm/contact">contact us</a>.
</p>

<h2>About this Service</h2>
<p>
This service provides methods to get both setlists and components of setlists such as artists, cities, countries or
venues.
</p>

<h2>Supported Content Types</h2>
<p>
The REST service currently supports XML (default) and JSON content.
</p>
<p>
To receive a JSON response, set the <code>Accept</code>
<a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.1">header</a> to <em>application/json</em>.
</p>

<h2>Internationalization</h2>
<p>
<small>(Please note that this is an experimental feature and does not work for all cities!)</small>
</p>
<p>
Most of the featured methods honor the <code>Accept-Language</code>
<a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4">header</a>. This header is used for
localizing cities and countries. The default language is English (en), but you can provide any of the languages
Spanish (es), French (fr), German (de), Portuguese (pt), Turkish (tr), Italian (it) or Polish (pl).
</p>
<p>
E.g. if you search a setlist for a concert that took place in Vienna and you pass &quot;de&quot; as header, you'll
get <em>&quot;Wien, &Ouml;sterreich&quot;</em> instead of <em>&quot;Vienna, Austria&quot;</em>.<br/>
This also works if you use a different language than the country's native language.
</p>
<p>
E.g. for a concert in New York, you'll get <em>&quot;Nueva York, Estados Unidos&quot;</em> instead of <em>&quot;New
York, United States&quot;</em> if you pass &quot;es&quot; as language.
</p>

<h2>API Keys</h2>

API keys (<a href="https://www.setlist.fm/settings/api">application form</a>) must be included in the request with
the <code>x-api-key</code> header.

<h2>Version History</h2>
<table class="table table-bordered table-versions">
<thead>
<tr>
<th>Version</th>
<th>Docs</th>
<th>End of Service</th>
</tr>
</thead> <tbody>
<tr>
<td><strong>1.0</strong></td>
<td><a href="/docs/1.0">Docs</a></td>
<td>-</li>
</tr>
<tr>
<td><strong>0.1</strong></td>
<td></td>
<td>December 31, 2017</li>
</tr>
</tbody>
</table>

## Authorization

This API does not require authorization.

## Actions

### .

> <p><br/>
> Returns an artist for a given Musicbrainz MBID<br/>
> </p>

*Tags:* `/1.0/artist/{mbid}`

#### Input Parameters
* `mbid` - _required_ - a Musicbrainz MBID, e.g. 0bfba3d3-6a04-4779-bb0a-df07df5b0558

### .

> <p><br/>
> Get a list of an artist's setlists.<br/>
> </p>

*Tags:* `/1.0/artist/{mbid}/setlists`

#### Input Parameters
* `mbid` - _required_ - the Musicbrainz MBID of the artist
* `p` - _optional_ - the number of the result page

### Get a city by its unique geoId.

*Tags:* `/1.0/city/{geoId}`

#### Input Parameters
* `geoId` - _required_ - the city's geoId

### Search for artists.

*Tags:* `/1.0/search/artists`

#### Input Parameters
* `artistMbid` - _optional_ - the artist's Musicbrainz Identifier (mbid)
* `artistName` - _optional_ - the artist's name
* `artistTmid` - _optional_ - the artist's Ticketmaster Identifier (tmid)
* `p` - _optional_ - the number of the result page you'd like to have
* `sort` - _optional_ - the sort of the result, either sortName (default) or relevance

### Search for a city.

*Tags:* `/1.0/search/cities`

#### Input Parameters
* `country` - _optional_ - the city's country
* `name` - _optional_ - name of the city
* `p` - _optional_ - the number of the result page you'd like to have
* `state` - _optional_ - state the city lies in
* `stateCode` - _optional_ - state code the city lies in

### Get a complete list of all supported countries.

*Tags:* `/1.0/search/countries`

### Search for setlists.

*Tags:* `/1.0/search/setlists`

#### Input Parameters
* `artistMbid` - _optional_ - the artist's Musicbrainz Identifier (mbid)
* `artistName` - _optional_ - the artist's name
* `artistTmid` - _optional_ - the artist's Ticketmaster Identifier (tmid)
* `cityId` - _optional_ - the city's geoId
* `cityName` - _optional_ - the name of the city
* `countryCode` - _optional_ - the country code
* `date` - _optional_ - the date of the event (format dd-MM-yyyy)
* `lastFm` - _optional_ - the event's Last.fm Event ID (deprecated)
* `lastUpdated` - _optional_ - the date and time (UTC) when this setlist was last updated (format yyyyMMddHHmmss) - either edited or
reverted. search will return setlists that were updated on or after this date
* `p` - _optional_ - the number of the result page
* `state` - _optional_ - the state
* `stateCode` - _optional_ - the state code
* `tourName` - _optional_
* `venueId` - _optional_ - the venue id
* `venueName` - _optional_ - the name of the venue
* `year` - _optional_ - the year of the event

### Search for venues.

*Tags:* `/1.0/search/venues`

#### Input Parameters
* `cityId` - _optional_ - the city's geoId
* `cityName` - _optional_ - name of the city where the venue is located
* `country` - _optional_ - the city's country
* `name` - _optional_ - name of the venue
* `p` - _optional_ - the number of the result page you'd like to have
* `state` - _optional_ - the city's state
* `stateCode` - _optional_ - the city's state code

### .

> <p><br/>
> Returns a setlist for the given versionId. The setlist returned isn't necessarily the most recent version. E.g.<br/>
> if you pass the versionId of a setlist that got edited since you last accessed it, you'll get the same version as<br/>
> last time.<br/>
> </p>

*Tags:* `/1.0/setlist/version/{versionId}`

#### Input Parameters
* `versionId` - _required_ - the version id

### .

> <p><br/>
> Returns the current version of a setlist. E.g. if you pass the id of a setlist that got edited since you last<br/>
> accessed it, you'll get the current version.<br/>
> </p>

*Tags:* `/1.0/setlist/{setlistId}`

#### Input Parameters
* `setlistId` - _required_ - the setlist id

### Get a user by userId.

*Tags:* `/1.0/user/{userId}`

#### Input Parameters
* `userId` - _required_ - the user's userId

### .

> <p><br/>
> Get a list of setlists of concerts attended by a user.<br/>
> </p>

*Tags:* `/1.0/user/{userId}/attended`

#### Input Parameters
* `userId` - _required_ - the user's userId
* `p` - _optional_ - the number of the result page

### .

> <p><br/>
> Get a list of setlists of concerts edited by a user. The list contains the current version, not the version<br/>
> edited.<br/>
> </p>

*Tags:* `/1.0/user/{userId}/edited`

#### Input Parameters
* `userId` - _required_ - the user's userId
* `p` - _optional_ - the number of the result page

### Get a venue by its unique id.

*Tags:* `/1.0/venue/{venueId}`

#### Input Parameters
* `venueId` - _required_ - the venue's id

### .

> <p><br/>
> Get setlists for a specific venue.<br/>
> </p>

*Tags:* `/1.0/venue/{venueId}/setlists`

#### Input Parameters
* `venueId` - _required_ - the id of the venue
* `p` - _optional_ - the number of the result page

## License

**flow**ground :- Telekom iPaaS / setlist-fm-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
