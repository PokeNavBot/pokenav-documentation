# Developer's Guide

## Audience

This document is intended for developers and researchers wishing to get access to PokeNav's data for the purposes of building third party tools, infographics or performing research. If you are simply trying to use PokeNav, you can skip the rest of this document.

## Attribution and Terms

You may use any data provided through the public APIs and datasets documented below, free of charge (except in case where a charge may be imposed by a third party you use to access said data). No warranty or gaurantee of accuracy is provided. All data in PokeNav is user submitted and as such is subject to errors. No personally identifiable information is present in the open data API.

The only condition of use is attribution.

### Attribution

If you use any PokeNav in anything that is republished publicly in the form of a tool, website, article, infographic or social media post; please provide a link back to our website. No specific format is required, but we suggest something like `Data provided by PokeNav - https://pokenavbot.com`. 

### Community Attribution

If you republish a live data (raid, research, etc) on a third party tool such as a map, website or mobile application, you must provide attribution for both PokeNav and the reporting community. Additionally, you must link to the community if the invite url is present.

## Data Availability

By default, all PokeNav communities opt into third party access. This means that any time a raid is reported, it will appear both in the PokeNav app and published for use by third parties. However, some communities choose not to share their data with third parties, and may opt out.


## APIs


### Raid Stream API

#### Endpoint

`https://api.pokenavbot.com/raids/v1/stream?lookback=<minutes>`

#### Params


<dl>
    <dt>lookback</dt>
    <dd>Integer, minutes to lookback from the last cached time (supported values: 1, 2, 5, 10).</dd>
</dl>

#### Description

Returns back a paginated list of raids that have changed in PokeNav in the lookback period.

#### Behavior & Usage Guide

This API is cached, and returns all created and updated raids, ordered by most recently updated, since the last cache period.

Updates are gauranteed to be cached / delayed by no more than 60 seconds. Pulling more frequently than 60 seconds is not advised, and will not consistently return new data.

Recommended usage pattern is to pull from the stream at a usage interval of N, where 60 <= N < lookback seconds. See usage example for a real world use of the raid stream.

You should use `updated` field to determine if a record is newer for a given raid.

#### Output Example


```
{
    "count": 64,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 152446,
            "hatches": "2018-11-08T21:43:01.420082Z",
            "ends": "2018-11-08T22:28:01.420082Z",
            "updated": "2018-11-08T21:54:25.814881Z",
            "egg_tier": null,
            "form": {
                "name": "togetic",
                "display_name": "Togetic",
                "raid_boss_level": 4
            },
            "gym": {
                "id": 441820,
                "name": "Woven Willow Dragon",
                "lat": 42.720723,
                "lon": -84.473375
            },
            "community": {
                "id": 372,
                "name": "LansingPokemonGo",
                "member_count": 2660
				"invite_url": null
            }
        },
        {
            "id": 152445,
            "hatches": "2018-11-08T22:23:38.713152Z",
            "ends": "2018-11-08T23:08:38.713152Z",
            "updated": "2018-11-08T21:53:54.936737Z",
            "egg_tier": 4,
            "form": null,
            "gym": {
                "id": 41087,
                "name": "Indian Rock",
                "lat": 39.400208,
                "lon": -76.477885
            },
            "community": {
                "id": 164,
                "name": "Pokémon Go White Marsh",
                "member_count": 645,
				"invite_url": null
            }
        },
...
```

#### Usage Example

[See the source code for the raid reports loader.](https://github.com/PokeNavBot/pokenav-open-data/blob/master/src/pokenav_data/raid_reports_loader.py)

### General API Notes

In PokeNav's APIs, the pagination links `next` & `previous` are path fragments (i.e. `/raids/v1/stream/?limit=1&lookback=10&offset=1`). You must recombine them with the endpoint host `https://api.pokenavbot.com` to access the next page.

## Public Datasets

PokeNav provides a set of datasets based on its public APIs, that enable anyone to slice and dice historical data. These are hosted as public datasets on Google BigQuery. Google Cloud Platform provides a generous free tier for querying this data.

The public dataset can be accessed by querying `pokenav-production.pokenav.*`. 

Currently available datasets:

    pokenav-production.pokenav.raid_reports


To test out querying through the bq web ui: [https://bigquery.cloud.google.com](https://bigquery.cloud.google.com)

Example query through the web ui (pulls the 10 most recently updated reports): 

`select * from [pokenav-production.pokenav.raid_reports] order by updated desc limit 10`

You could export the results to google sheets, json, etc.
