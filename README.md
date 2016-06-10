

## Welcome to Insomniac's api

All calls to Insomniac's API must be done to the following URL http://insomniac.cleverapps.io/, so for example if you want to call the galleries endpoint it would be like this:

http://insomniac.cleverapps.io/api/beta/galleries?key=your-api-key

### To Register for an API Key:

1. Be registered for the EDC Hackathon in SF, LA, or Las Vegas.
2. Email boris.polania@insomniac.com with your EDC Hackathon Team Name.


### Galleries

The gallery object contains the following information:

- id: A unique integer identifier for the gallery
- title: the gallery title
- description: a description of the gallery
- size: the size of the gallery
- images: an array of images.

### Getting all galleries

Returns all available galleries. Send a GET request to the galleries endpoint /api/beta/galleries.

```
http://insomniac.cleverapps.io/api/beta/galleries?key=your-api-key
```

The response is a 200 JSON object with an array of galleries.

<sub>[//]: <> TODO: add curl request structure</sub></br>
<sub>[//]: <> TODO: add full fields description</sub></br>
<sub>[//]: <> TODO: add full endpoint description</sub>

Response Example:

```
	{
	    "data": [{
			"id": "KJHPok",
	        "title": "EDC NYC 2016!!!",
	        "description": null,
	        "size": 12,
					"images": ...
	    },
		{
	        "id": "OPnmLK",
	        "title": "EDC Las Vegas 2016!!!",
	        "description": null,
	        "size": 24,
					"images": ...
	    }],
	    "success" : true,
	    "status" : 200
	}
```

### Getting a gallery by id

To do this, send a GET request to /api/beta/gallery/{gallery_id} endpoint.

```
http://insomniac.cleverapps.io/api/beta/galleries/{gallery_id}?key=your-api-key
```

The response is a 200 JSON object with an array of galleries matching the specified id.

<sub>[//]: <> TODO: add curl request structure</sub></br>
<sub>[//]: <> TODO: add full fields description</sub></br>
<sub>[//]: <> TODO: add full endpoint description</sub>

Response Example:

```
	{
			"id": "jk9KNK7",
			"title": "EDC NYC 2016 Gallery",
			"description": "This is the gallery for EDC NYC 2016",
			"size": 3,
			"images": [{
	        "id": "Yvlkl",
	        "title": "DJ Boris Performing 1",
	        "description": null,
	        "datetime": 5431658,
	        "type": "image/jpeg",
	        "width": 3200,
	        "height": 4500,
	        "size": 789541
	    },
			{
		        "id": "POlKHk",
		        "title": "DJ Boris Performing 2",
		        "description": null,
		        "datetime": 54319878,
		        "type": "image/jpeg-animated",
		        "width": 3200,
		        "height": 4500,
		        "size": 789532
		    },
				{
		        "id": "YhnMoL",
		        "title": "DJ Boris Performing 3",
		        "description": null,
		        "datetime": 5431658,
		        "type": "video/mp4",
						"duration":42587,
		        "width": 3200,
		        "height": 4500,
		        "size": 83403580
		    }],
	    "success" : true,
	    "status" : 200
	}
```

## Events

The event object contains the following information:

- id: a unique integer identifier for the event
- title: the title of the event
- url: URL of the event
- datetime_local: date/time of the event in the local timezone of the venue.
- datetime_utc: date and time of the event in UTC
- time_tbd: a boolean flag to signify that an event has a "to be determined" time.
- date_tbd: a boolean flag to signify that an event has a "to be determined" date. If this is True, datetime_utc and datetime_local should be treated as estimates
- performers: an list of performers
- venue: a venue response document
- short_title: a shortened title for the event
- score: a numerical representation of popularity based on ticket sales
- type: type of event

### Getting all events

Returns all available events. Send a GET request to the galleries endpoint /api/beta/events.

```
http://insomniac.cleverapps.io/api/beta/events?key=your-api-key
```

The response is a 200 JSON object with an array of events.

<sub>[//]: <> TODO: add curl request structure</sub></br>
<sub>[//]: <> TODO: add full fields description</sub></br>
<sub>[//]: <> TODO: add full endpoint description</sub>

Response Example:

```
	{
	    "id": 3249846,
		"title": "EDC NYC",
	    "url": "http://newyork.electricdaisycarnival.com/",
	    "datetime_local": "2016-05-14T20:00:00",
	    "performers": [
	        {
	            "name": "DJ Boris",
	            "short_name": "DJ B",
	            "url": "https://www.djboris.com",
	            "image": "kjkYjkhk",
	            "primary": true,
	            "id": 1234,
	            "score": 1524,
	            "type": "band",
	            "slug": "dj-b"
	        },
	        {
	            "name": "Los Callate Agustin",
	            "short_name": "Los Callate",
	            "url": "https://www.loscallate.com",
	            "image": null,
	            "id": 1235,
	            "score": 1789,
	            "type": "band",
	            "slug": "los-callate"
	        }
	    ],
	    "venue": {
	        "city": "New York",
	        "name": "Citi Field",
	        "extended_address": null,
	        "url": "http://newyork.mets.mlb.com/nym/ballpark/",
	        "country": "US",
	        "state": "NY",
	        "postal_code": "10019",
	        "location": {
	            "lat": 10.00,
	            "lon": -20.00
	        },
	        "address": null,
	        "id": 111
	    },
	    "short_title": "EDC NYC",
	    "datetime_utc": "2016-04-10T00:00:00",
	    "type": "concert"
	}

```

### Getting an event by id

To do this, send a GET request to /api/beta/events/{event_id} endpoint.

```
http://insomniac.cleverapps.io/api/beta/events/{event_id}?key=your-api-key
```

The response is a 200 JSON object with the event matching the specified id.

Response Example:

```
	{
	    "id": 3249846,
		"title": "EDC NYC",
	    "url": "http://newyork.electricdaisycarnival.com/",
	    "datetime_local": "2016-05-14T20:00:00",
	    "performers": [
	        {
	            "name": "DJ Boris",
	            "short_name": "DJ B",
	            "url": "https://www.djboris.com",
	            "image": "kjkYjkhk",
	            "primary": true,
	            "id": 1234,
	            "score": 1524,
	            "type": "band",
	            "slug": "dj-b"
	        },
	        {
	            "name": "Los Callate Agustin",
	            "short_name": "Los Callate",
	            "url": "https://www.loscallate.com",
	            "image": null,
	            "id": 1235,
	            "score": 1789,
	            "type": "band",
	            "slug": "los-callate"
	        }
	    ],
	    "venue": {
	        "city": "New York",
	        "name": "Citi Field",
	        "extended_address": null,
	        "url": "http://newyork.mets.mlb.com/nym/ballpark/",
	        "country": "US",
	        "state": "NY",
	        "postal_code": "10019",
	        "location": {
	            "lat": 10.00,
	            "lon": -20.00
	        },
	        "address": null,
	        "id": 111
	    },
	    "short_title": "EDC NYC",
	    "datetime_utc": "2016-04-10T00:00:00",
	    "type": "concert"
	}

```


### Getting an event by performer

The performers argument is used to scope the result set to specific performers.

```
http://insomniac.cleverapps.io/api/beta/events?performer=performer_name&key=your-api-key
```

The response is a 200 JSON object with an array of events matching the specified performer.

Response Example:

```
	{
	    "id": 3249846,
		"title": "EDC NYC",
	    "url": "http://newyork.electricdaisycarnival.com/",
	    "datetime_local": "2016-05-14T20:00:00",
	    "performers": [
	        {
	            "name": "DJ Boris",
	            "short_name": "DJ B",
	            "url": "https://www.djboris.com",
	            "image": "kjkYjkhk",
	            "primary": true,
	            "id": 1234,
	            "score": 1524,
	            "type": "band",
	            "slug": "dj-b"
	        },
	        {
	            "name": "Los Callate Agustin",
	            "short_name": "Los Callate",
	            "url": "https://www.loscallate.com",
	            "image": null,
	            "id": 1235,
	            "score": 1789,
	            "type": "band",
	            "slug": "los-callate"
	        }
	    ],
	    "venue": {
	        "city": "New York",
	        "name": "Citi Field",
	        "extended_address": null,
	        "url": "http://newyork.mets.mlb.com/nym/ballpark/",
	        "country": "US",
	        "state": "NY",
	        "postal_code": "10019",
	        "location": {
	            "lat": 10.00,
	            "lon": -20.00
	        },
	        "address": null,
	        "id": 111
	    },
	    "short_title": "EDC NYC",
	    "datetime_utc": "2016-04-10T00:00:00",
	    "type": "concert"
	}

```


### Getting an event by venue

The venue argument is used to scope the result set to specific a specific venue.

```
http://insomniac.cleverapps.io/api/beta/events?venue=venue_name&key=your-api-key
```

The response is a 200 JSON object with an array of events matching the specified venue.

Response Example:

```
	{
	    "id": 3249846,
		"title": "EDC NYC",
	    "url": "http://newyork.electricdaisycarnival.com/",
	    "datetime_local": "2016-05-14T20:00:00",
	    "performers": [
	        {
	            "name": "DJ Boris",
	            "short_name": "DJ B",
	            "url": "https://www.djboris.com",
	            "image": "kjkYjkhk",
	            "primary": true,
	            "id": 1234,
	            "score": 1524,
	            "type": "band",
	            "slug": "dj-b"
	        },
	        {
	            "name": "Los Callate Agustin",
	            "short_name": "Los Callate",
	            "url": "https://www.loscallate.com",
	            "image": null,
	            "id": 1235,
	            "score": 1789,
	            "type": "band",
	            "slug": "los-callate"
	        }
	    ],
	    "venue": {
	        "city": "New York",
	        "name": "Citi Field",
	        "extended_address": null,
	        "url": "http://newyork.mets.mlb.com/nym/ballpark/",
	        "country": "US",
	        "state": "NY",
	        "postal_code": "10019",
	        "location": {
	            "lat": 10.00,
	            "lon": -20.00
	        },
	        "address": null,
	        "id": 111
	    },
	    "short_title": "EDC NYC",
	    "datetime_utc": "2016-04-10T00:00:00",
	    "type": "concert"
	}

```

## Performers

The performer object contains the following information:

- id: a unique integer identifier for the performer
- name: the performer name
- short_name: a short name for the performer
- url: URL associated to the performer
- image: an image associated to this performer
- score: a numerical representation of popularity
- slug: performer slug

### Getting all performers

Returns all available performers. Send a GET request to the performers endpoint /api/beta/performers.

```
http://insomniac.cleverapps.io/api/beta/performers?key=your-api-key
```

The response is a 200 JSON object with an array of performers.

<sub>[//]: <> TODO: add curl request structure</sub></br>
<sub>[//]: <> TODO: add full fields description</sub></br>
<sub>[//]: <> TODO: add full endpoint description</sub>

Response Example:

```
	{
	    "data": [
	        {
	            "name": "DJ Boris",
	            "short_name": "DJ B",
	            "url": "https://www.djboris.com",
	            "image": "kjkYjkhk",
	            "primary": true,
	            "id": 1234,
	            "score": 1524,
	            "type": "band",
	            "slug": "dj-b"
	        },
	        {
	            "name": "Los Callate Agustin",
	            "short_name": "Los Callate",
	            "url": "https://www.loscallate.com",
	            "image": null,
	            "id": 1235,
	            "score": 1789,
	            "type": "band",
	            "slug": "los-callate"
	        }],
	    "success" : true,
	    "status" : 200
	}
```
### Getting a performer by id

To do this, send a GET request to /api/beta/performers/{performer_id} endpoint.

```
http://insomniac.cleverapps.io/api/beta/events/{performer_id}?key=your-api-key
```

The response is a 200 JSON object with the performer matching the specified id.

Response Example:

```
	{
	    "data": [
	        {
	            "name": "DJ Boris",
	            "short_name": "DJ B",
	            "url": "https://www.djboris.com",
	            "image": "kjkYjkhk",
	            "primary": true,
	            "id": 1234,
	            "score": 1524,
	            "type": "band",
	            "slug": "dj-b"
	        }],
	    "success" : true,
	    "status" : 200
	}
```
## Venues

The venue object contains the following information:

- id: a unique integer identifier for the venue
- name: the venue name
- url: URL associated to the venue
- street: street for the venue address
- country: country for the venue address
- city: city for the venue address
- state: state for the venue address
- postal_code: postal code for the venue address
- location: location for the venue address

### Getting all venues

Returns all available venues. Send a GET request to the venues endpoint /api/beta/venues.

```
http://insomniac.cleverapps.io/api/beta/venues?key=your-api-key
```

The response is a 200 JSON object with an array of venues.

<sub>[//]: <> TODO: add curl request structure</sub></br>
<sub>[//]: <> TODO: add full fields description</sub></br>
<sub>[//]: <> TODO: add full endpoint description</sub>

Response Example:

```
	{
	    "data": [
			{
					"city": "New York",
					"name": "Citi Field",
					"street": null,
					"url": "http://newyork.mets.mlb.com/nym/ballpark/",
					"country": "US",
					"state": "NY",
					"postal_code": "10019",
					"location": {
							"lat": 10.00,
							"lon": -20.00
					},
					"address": null,
					"id": 111
			},
			{
					"city": "Hollywood",
					"name": "Hollywood Arena",
					"street": null,
					"url": "http://hollywood-arena.com/fl/arena/",
					"country": "US",
					"state": "FL",
					"postal_code": "33020",
					"location": {
							"lat": 10.00,
							"lon": -20.00
					},
					"address": null,
					"id": 111
			}],
	    "success" : true,
	    "status" : 200
	}
```
### Getting a venue by id

To do this, send a GET venue to /api/beta/venues/{venue_id} endpoint.

```
http://insomniac.cleverapps.io/api/beta/venues/{venue_id}?key=your-api-key
```

The response is a 200 JSON object with the venue matching the specified id.

Response Example:

```
	{
	    "data": [
			{
					"city": "New York",
					"name": "Citi Field",
					"extended_address": null,
					"url": "http://newyork.mets.mlb.com/nym/ballpark/",
					"country": "US",
					"state": "NY",
					"postal_code": "10019",
					"location": {
							"lat": 10.00,
							"lon": -20.00
					},
					"address": null,
					"id": 111
			}],
	    "success" : true,
	    "status" : 200
	}
```