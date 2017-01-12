# Overview

## General information 

```
GET /crew/[CREW_NAME]
```

Shows general information about the crew, like the crew id which is importent for a bunch of other requests, crew tag, the crew logo, rank titles as well as the permissions. 

## Emblems 

```
GET /crew/[CREW_NAME]
```

(same endpoint as "General information", data hidden in `<script>` tags)

Returns the first four crew emblems and it's image location.

## Crew feed 

```
GET /reference/crewfeed/[CREW_ID]
```

Structured JSON data of all the crew feed messages and events.

## Snapmatic pictures

```
GET /crewapi/[CREW_NAME]/gtav/photo
```

Returns the four latest crew snapmatic pictures as well as the total count. 

## Content creator jobs

```
GET /crewapi/[CREW_NAME]/gtav/job
```

Returns the latest job as well as the total count. 
