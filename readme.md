# Youtube Search API

Youtube Search API is an API for getting Youtube search results.

## Installation

```bash
npm install youtube-search-api
```

## Usage (import)

```node
const youtubesearchapi=require('youtube-search-api');
```
## GetListByKeywords (Promise)
```node
youtubesearchapi.GetListByKeyword("<keywords>",[playlist boolean],[limit number])
```
GetListByKeywords Result
```node
{items:[],nextPage:{nextPageToken:"xxxxxxxx",nextPageContext:{}}}
```
"items" is the array from youtube, "nextPage" needs to pass when going to the next page. If playlist arg is true, will return ```type:'playlist'``` but the ```videos:[]``` property will not return the whole videos in the list, need to call ```GetPlaylistData``` to get real playlist's videos. Item with Video type will return ```isLive=[true/false]``` to identify live video or not.
## NextPage (Promise)
```node
youtubesearchapi.NextPage(<nextPage from GetListByKeywords result>,[playlist boolean],[limit number])
```
NextPage Result
```node
{items:[],nextPage:{nextPageToken:"xxxxxxxx",nextPageContext:{}}}
```
Item with Video type will return ```isLive=[true/false]``` to identify live video or not.

## Playlist with ID (Promise)
```node
youtubesearchapi.GetPlaylistData(<Playlist Id>,[limit number])
```
Playlist Result
```node
{items:[],metadata:{}}
```

## Get Suggest Data (Promise)
```node
youtubesearchapi.GetSuggestData([limit number])
```
Suggest Data Result
```node
{items:[]}
```
Item with Video type will return ```isLive=[true/false]``` to identify live video or not.

## Get Channel by channel Id (Promise)
```node
youtubesearchapi.GetChannelById(<channel ID>)
```
Channel Data Results
```node
[
  [ { title: '[title]', content: [Object] } ]
]
```
Will return tabs in array format.

## Message
If you want to work with me to fix bug or implement new idea. You are available to send me some new idea of this project.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## TODO
1. Support front-end (Vue, React) (On going)

## Bug fixed

## Update
1. channelTitle add into return items. (by SirBob01) (https://github.com/SirBob01)
2. Implemented results limit parameter for all functions (by ElyasAsmad) (https://github.com/ElyasAsmad)
3. async/await implemented


## License
[MIT](https://choosealicense.com/licenses/mit/)