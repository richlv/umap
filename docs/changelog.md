# Changelog

## 1.4.1 - 2023-07-17

- fix tooltip position, after Leaflet upgrade (cf #1207)
- replace `mousewheel` event by `wheel`, to follow Leaflet change (cf #1211)
- fallback user to dashboard after OAuth process (cf #1208)
- add share status in user dashboard (cf #1209)

## 1.4.0 - 2023-07-15
- add basic version of a "My Dashboard" page (cf #1196)
- better fit iframe in popups (cf #1203)
- fix missing line edit icons (cf #1205)
- bump Leaflet from 1.3.4 to 1.9.4 (cf #1201)
- fix permissions panel empty at first save (cf #1200)
- add `overflow-x: hidden` to popup (cf #1198)
- add time in datalayer versions list (cf #1195)

## 1.3.7 - 2023-07-03

- changed datalayer and tilelayer icons (cf #1188)
- fixed wrong language code passed to `localeCompare` (cf #1190)
- fixed natural sort of feature not placing space before other chars (cf #1191)

## 1.3.6 - 2023-07-01

- set font-display: swap; for fonts definition
- do not force scroll on popup content
- document Shift-Click and add Ctrl-Shift-click to edit datalayer
- advanced filter should not affect non browsable layers
- expose 'locale' parameter in templates
- pass options at datalayer creation when importing from umap file
- allow to set the lang while generating an anonymous_edit_url
- control links target
- allow to use properties as color value
- add "delete" link in data browser
- more natural sort of features
- be more strict when coordinates are set manually
- allow to sort reverse
- handle CORS errors with an explicit message
- add basic doc about settings
- add umap command in Docker PATH
- add a setting for the number of maps per search
- use SVG icons
- display latest created maps on empty search

## 1.3.5 - 2023-06-17

- fix stars link in header

## 1.3.4 - 2023-06-17

- allow to control icon opacity (cf #236)
- display the number of maps on search results page
- allow to customize user display name and URL slug
- fix geo: scheme in (description) links (cf #1140)
- fix popup footer floating within the content (cf #1146)

## 1.3.3 - 2023-06-07

- add Dockerfile
- fix content overlflow on popups (cf #1128)
- display uMap version in the credit box + link to changelog (cf #1129)

## 1.3.2 - 2023-06-04

- fix wrong message after creating a map while authenticated
- display user name in the map edit toolbar when authenticated

## 1.3.1 - 2023-06-03

- fix table rendering (cf #1117)
- fix some errors not caught in ajax proxy (cf #1118 #1119)
- add simple form to send secret edit link by email in anonymous mode (cf #1102)

## 1.3.0 - 2023-05-31

- added a filter by category panel (cf #1041, thanks @k-3st3ban)
- added a permanent credit (cf #1041, thanks @k-3st3ban)
- allow to add an overlay tilelayer
- replaced custom locate control with Leaflet.Locate (cf #1031, thanks @aleksejspopovs)
- fixed bug where we coud not edit permissions of a new saved map unless reloading the page
- CSS: Fix cut of text in iframes of popup content (cf #971, thanks @tordans)
- enhanced property fallback in string formatting (cf #862, thanks @mstock)
- lines and polygons measure is now displayed while drawing (cf #1068, thanks @knowname)
- refactored zoomTo while making easing transition non default (cf #679 #179)
- fixed old `_storage_options` not being cleaned when saving map (cf #1076)
- added star maps feature (cf #683)
- added a banner + removed create buttons when in read only mode (cf #1095)
- added DOMPurify to escape malicious input from user (cf #1094)
- expose direct map URL in the export panel (cf #699)
- added a very basic `/stats/` JSON view (cf #1100)
- added max width for the help box (on small screens, cf #887)
- display the steps for inputs of type range (cf #877)
- lazy load tile layers thumbnails (cf #1089)
- allow geolocation from iframe embeds (cf #898)
- remove the limit of visible maps in user’s view (cf #1025)
- switch to Django full text search instead of home made (cf #519)

## 1.2.7
- redirect to `user_maps` at auth end when `window.opener` is unavailable (Twitter auth flow)

## 1.2.6
- marked User.id as protected, to fix Twitter auth

## 1.2.5
- Allow to create search index without changing unaccent mutability (cf #519)
- switched from `If-None-Match` to `If-Unmodified-Since` for concurrency control
- prevent caching datalayers geojson when in edit mode
- refactored gzip management

## 1.2.4
- upgrade to Django 4.x, and upgrade of other deps
- switched from custom DictField to propert JsonField

## 1.2.3

- improved panel layout and image sizing (by @Binnette, cf #824)
- upgraded Django to 2.2.17 and Pillow 8.0.1 (which drops support for python 3.5)
- experimental fallback handling in templating (cf #820)
- fixed search URL, and allow to control it from settings (cf #842)
- fixed map frozen when setting by hand invalid coordinates (cf #799)
- fixed changing map ownership (cf #780)
- do not change map zoom when locating user (cf #763)
- update map extent on first save if it has not been changed yet (cf #841)


## 1.2.2

- fixed bug in popup inner HTML (cf #776)

## 1.2.1

- minimal RTL support (cf #752)
- fix username URL regex to allow spaces (cf #774)

## 1.2.0

- added translations for ar, ast, et, he, id, is, no, pt-br, pt-pt, si-lk, sr,
  sv, th-th, tr
- fixed username not updated when login with OAuth (by @Binnette, cf #754)
- removed protocol from iframe URL (by @Binnette, cf #748)
- fixed icon max-height (cf #143)
- better image and iframe sizing in right panel (cf #184)
- allow to use variables for tooltips (cf #737)
- add a marker on user geolocation (cf #339)
- change arrow direction when "more controls" is active (cf #485)
- add an experimental feature permalink (cf #294)
- fixed edge case where slideshow will run even when inactive
- fixed bug when trying to add a property with a dot in the name (cf #426)

## 1.1.2

- fixed parsing of two iframes
- updated i18n
- upgraded Django to 2.2.1 and psycopg2 to 2.8.1

## 1.1.1

- downgraded psycopg2 to 2.7.7 (migrations where failing); should be fixed with
  Django 2.2.1
- fixed annoying bug where "load more map" would fail
- allow to filter by share status in admin page

## 1.1.0

- added `Map.BLOCKED` share status, to redact maps issuing legal complaints
  (only available through the admin)
- replaced `DictField` by `JSONField` (`umap migrate` needed)
- added `search_fields` and `autocomplete_fields` to MapAdmin
- lowercase `frameborder` in iframe export
- fixed bug in slideshow since renaming of Leaflet.Storage

## 1.0.0

### Upgrading to 1.0

- because of the merge of django-leaflet-storage inside umap, the migrations
  has been reset, so a bit of SQL needs to be ran by hand:

```sql
BEGIN;
DELETE FROM django_migrations WHERE app = 'leaflet_storage';
DELETE FROM django_migrations WHERE app = 'umap';
ALTER TABLE leaflet_storage_datalayer RENAME TO umap_datalayer;
ALTER TABLE leaflet_storage_datalayer_id_seq RENAME TO umap_datalayer_id_seq;
ALTER TABLE leaflet_storage_licence RENAME TO umap_licence;
ALTER TABLE leaflet_storage_licence_id_seq RENAME TO umap_licence_id_seq;
ALTER TABLE leaflet_storage_map RENAME TO umap_map;
ALTER TABLE leaflet_storage_map_editors RENAME TO umap_map_editors;
ALTER TABLE leaflet_storage_map_editors_id_seq RENAME TO umap_map_editors_id_seq;
ALTER TABLE leaflet_storage_map_id_seq RENAME TO umap_map_id_seq;
ALTER TABLE leaflet_storage_pictogram RENAME TO umap_pictogram;
ALTER TABLE leaflet_storage_pictogram_id_seq RENAME TO umap_pictogram_id_seq;
ALTER TABLE leaflet_storage_tilelayer RENAME TO umap_tilelayer;
ALTER TABLE leaflet_storage_tilelayer_id_seq RENAME TO umap_tilelayer_id_seq;
COMMIT;
```

- Then fake initial migrations:

        umap migrate --fake-initial

- If you have customized some templates, change any `leaflet_storage/` path
  to `umap/`

- If you have customized some static, change any `storage/` path
  to `umap/`

- Each `LEAFLET_STORAGE_XXX` setting should be renamed in `UMAP_XXX` (but we
  still support them for now)

- If you still have a `MIDDLEWARE_CLASSES` setting, rename to `MIDDLEWARE`

- uMap now loads the local configuration from /etc/umap/umap.conf if
  `UMAP_SETTINGS` is not set, so you may want to use that path and remove
  the env var setting

- As usual, remember to update statics:

        umap collectstatic
        umap compress


### 1.0.0-rc.9
- increased maps displayed in user maps page (cf #651)
- exposed original map url in full export (cf #659)


### 1.0.0-rc.8

- fixed non browsable missing in caption panel
- fixed remote datalayers missing in browse data panel when displayed on load (cf #509)

### 1.0.0-rc.7

- fixed table popup template not displaying name anymore (cf #647)

### 1.0.0-rc.6

- fixed OSM properties not read anymore (cf #641)
- fixed permissions panel not active at first map save

### 1.0.0-rc.5

- fixed user autocompletion in permissions panel (cf #635)
- fixed ternary choice dealing with unknown values (cf #633)

### 1.0.0-rc.4

- fixed geodjango defaulting geojson parsing to SRID 3857 instead of 4326
- fixed tooltip on hover (cf #631)


### 1.0.0-rc.3

- added a readonly mode (`UMAP_READONLY=True`), useful to disallow update while
  migrating from one server to an other, for example


### 1.0.0-rc.2

- allow to cache proxied remote data requests (#513 #510 #160)
- fixed popup template parsing of url with url as query string (#607)
- naive support for nested variables in templates (#600)
- Removed Map.tilelayer foreignkey
- split popupTemplate in popupShape and popupTemplate: popupShape is for
  choosing between proper popup and panel, while popupTemplate now will allow
  to choose between default "name + description" mode, or table, or geoRSS ones.
  Allows to add more of those in the future also.
- fixed popup not opening on first zoom button click when marker is clustered (#611)

### 1.0.0-rc.1
- BREAKING: support of python 2 is removed per upgrading to Django 2.0
- WARNING: merge Leaflet-Storage and django-leaflet-storage inside umap to ease
  maintenance and contribution; See [Upgrading to 1.0](#upgrading-to-1.0)
- permissions management forms are now built in JS directly
- upgrade all dependencies
- added a language switcher in the home page footer
- added UMAP_CUSTOM_TEMPLATES and UMAP_CUSTOM_STATICS settings to make
  customization easier
- added empty `umap/theme.css` to ease customization
- add download link in the map and datalayers edit panel
- fixed some touch related CSS issues
- removed support for old URL (changed in version `0.3.0`)
- added languages: hr (Croatian), pl (Polish), hu (Hungarian), sl (Slovenian),
  el (Greek), gl (Galician)
- JS locales are now bundled, no need to generate them while installing
- local settings are now loaded from `/etc/umap/umap.conf` if available
- fixed an issue where it was not possible to change the tilelayer if the
  tilelayer control was not added to the map (#587)
- `showLabel` is now a ternary value (instead of having this plus `labelHover`)
  (#553)
- fixed resetting a select to undefined for inheritable fields (#551)
- fixed labelKey not being saved (#595)
- filtering in data browser now is also reflected in the displayed features
  (#550)
- fixed ClusterMarker text color on Chrome (#547)
- allow to clone also markers
- only list https ready tilerlayers when page is in https (#567)
- allow to use an unicode character as Marker symbol (#527)
- add `{rank}` as dynamic feature property (to be used in popup or icon symbol)
- add an explicit button to attach a owner to an anonyous map (#568)
- Add 'TablePanel' popup template (#481)


## 0.8.0
- allow colon in properties to be consumed in popupTemplate
- added am_ET, pl and sk_SK locales
- fixed default licence being created in every available languages
- switch to pytest for unit tests
- Django 1.10 compatibility
- add DataLayer.rank
- Expose DataLayer versions
- python3 support
- add nofollow meta when map is not public

## 0.7.5
- upgrade osmtogeojson to 2.1.0
- localize and proxy dataUrl parameter

## 0.7.4
- fix anonymous not able to edit map anymore

## 0.7.3
- add tooltip when drawing
- import multiple files at a time
- added Chinese (Taiwan) locale
- fixed right-click on path vertex not working propertly when editing

## 0.7.1
- upgrade Leaflet.Editable to 0.2.0
- fixed some bugs after Leaflet.Editable switch

## 0.7.0
- introduce panel popup mode
- upgraded leaflet.loading to 0.1.10
- make the cluster text color dynamic
- fix missing icons for transorm to polygon/polyline actions
- add a slideshow mode
- make possible to set cluster color by hand
- make possible to manage showLabel from layer and map
- basic kml/gpx download support
- MultiLineString are merged at import
- catch setMaxBounds errors (when using useless bounds)
- first version of a table editor
- it's now possible to cancel every mouse action of a polygon
  (useful when using them as background)
- simple custom popup templates
- more control over map data attribution (custom inputs added)
- basic HTTP optimistic concurrency control
- add "empty" button in limit bounds fieldset
- make possible to decide which properties the data browser will filter on
- add "datalayers" query string parameter to override shown datalayers on map load
- add edit fieldset for changing marker latlng by hand
- moved from Leaflet.Draw to Leaflet.Editable
- added Vietnamese
- by default, allow_edit is now false
- added Chinese (Taiwan) locale

## 0.6.x
- add TMS option to custom tilelayer
- allow to define default properties at map level
- support iframe in text formatting
- fix bug where polygon export were adding a point
- make that only visible elements are downloaded
- iframe export helper
- add Leaflet.label (for marker only atm)
- GeoRSS support
- heatmap support, thanks to https://github.com/Leaflet/Leaflet.heat
- added optional caption bar
- added new "large" popup template
- added a button to empty a layer without deleting it
- added a button to clone a datalayer
- added dataUrl and dataFormat on map creation page
- basic support for GeometryCollection import
- removed submodules and switched to grunt for assets management
- upgrade to django 1.6
- sesql replaced by django-pgindex
- support for gzip for datalayer geojson
- support for X-Senfile/Accel-Redirect
- more translations
- fix anonymous map owner not able to delete their map
- fix missing vendors assets
- reset South migrations (some were bugged); to be back again with django 1.7
- added russian locale
- http optimistic concurrency control
- longer anonymous cookie max_age (one month instead of session only)
- add possibility to override default zoom with LEAFLET_ZOOM setting
- fix bug where anonymous map wasn't editable by logged in users even if
  edit status was ANONYMOUS

## 0.5.x
- datalayers are now sent to backend as geojson
- there is now a global "save" button, and also a "cancel changes"
- added a contextmenu, thanks to https://github.com/aratcliffe/Leaflet.contextmenu
- added a loader, thanks to https://github.com/ebrelsford/Leaflet.loading
- import are processed client side, thanks to https://github.com/mapbox/csv2geojson
  and https://github.com/mapbox/togeojson
- download is handled client side
- option "outlink" as been added, to open external URL on polygon click
- edit shortcuts has been added (Ctrl+E to toggle edit status, Ctrl+S to save, etc.)
- links in popup now open in a now window
- possibility to add custom icon symbols
- new option to clusterize markers, thanks to https://github.com/Leaflet/Leaflet.markercluster
- remote data option added to datalayer: this will fetch data from a given URL
  instead of from the local database
- popup window can now display a table with all features properties
- support of OSM XML format, thanks to https://github.com/tyrasd/osmtogeojson
- added a measure control, thanks to https://github.com/makinacorpus/Leaflet.MeasureControl
- added Transifex config
- simple help boxes
- it's now possible to set background layer with manual settings
- add an edit button in the data browser (when in edit mode)
- add icon URL formatting with feature properties
- add "Transform to Polygon/Polyline" action
- new link on contextmenu to open external routing service from clicked point
- fix bug where features were duplicated when datalayer was deleted then reverted
- add layer action to databrowser
- add optional default CSS
- allow to close panel by Ctrl+Enter when editing in textarea
- add management for map max bounds
- add Ctrl+Z for canceling changes
- internal storage structure totally reviewed: datalayers are stored as geojson files,
  instead of being split in features stored in PostGIS
- upload and download moved to client side (see Leaflet.Storage)
- cloned map name is now prefixed by "Clone of "
- added Transifex config
- workaround for non asciiable map names
- add a share_status fielf in Map model

## 0.4.x
- add a data browser
- add a popup footer with navigation between features
- some work on IE compat
- new tilelayer visual switcher
- Spanish translation, thanks to @ikks
- renamed internally category in datalayer
- add a rank column to tilelayer to control their order in the tilelayer edit box
- fix description that was not exported in the GeoJSON export
- return proper 403 if bad signature on anonymous_edit_url access
- refactored tilelayer management
- smarter encoding management at import
- smarter errors management at import
- handle other delimiters than just comma for CSV import
- Spanish translation, thanks to @ikks
- map clone possibility

## 0.3.x
- add a setting to display map caption on map load (cf #50)
- add nl translation
- update to Leaflet 0.6-dev and Leaflet.Draw 0.2
- handle anonymous map creation
- Fix color no more displayed in map info box (cf #70)
- portuguese translation (thanks @FranciscoDS)
- fix bug when the map title was too long (making the slug too long, and so over the
  database limit for this field)
- add a setting to display map caption on map load (cf Leaflet.Storage#50)
- update to django 1.5
- first version of a CSV import
- add a Textarea in import form
- first version of data export (GeoJSON only for now)


## 0.2.0
- handle auth from popup
- add a control for map settings management
- move to Leaflet 0.5
- move to Leaflet.draw 0.1.6
- default tooltip has now a fixed position
- make just drown polys editable
- handle path styling option (https://github.com/yohanboniface/Leaflet.Storage/issues/26)
- add an UI to manage icon style and picto (https://github.com/yohanboniface/django-leaflet-storage/issues/22)
- icon style and picto are now manageable also on Markers (https://github.com/yohanboniface/django-leaflet-storage/issues/21)
- add Leaflet.EditInOSM plugin in options
- add a scale control (optional)
- add an optional minimap (with Leaflet.MiniMap plugin)
- handle map settings management from front-end
- handle path styling options (https://github.com/yohanboniface/Leaflet.Storage/issues/26)
- remove Category.rank (https://github.com/yohanboniface/django-leaflet-storage/issues/46)
- Marker has now icon_class and pictogram fields (https://github.com/yohanboniface/django-leaflet-storage/issues/21)
- handle scale control
- basic short URL management
- fixed a bug where imports were failing if the category had a custom marker image

## 0.1.0

- first packaged version
