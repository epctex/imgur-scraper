[https://apify.com/epctex/imgur-scraper](https://apify.com/epctex/imgur-scraper?fpr=yhdrb)

# Actor - Imgur Scraper

## Imgur scraper

Since Imgur doesn't provide a good and free API, this actor should help you to retrieve data from it.

The Imgur data scraper supports the following features:

-   Search anything - You can search any keyword with any sorting or filtering option. Provide the options you require and retrieve everything in a blazing-fast manner!

-   Scrape tags - Looking for posts of a specific tag? No problem. Provide the URL and the Imgur Scraper will retrieve everything in no time.

-   Scrape posts of any user - You can retrieve all the posts of any user without any limits.

-   Scrape comments - If you are looking for the comments that have been added by the users, you are in the right place. Within the powerful algorithm of Imgur Scraper, you can extract all the comments (and replies) directly!

-   Scrape posts - Scrape very detailed information for each of the posts that you'd like to get.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/imgur-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on Imgur that should be visited. Required fields are:

- `search`: (Optional) (String) Keyword that you want to search on Imgur.

- `startUrls`: (Optional) (Array) List of Imgur URLs. You should only provide post detail, search, user, or tag URLs.

- `includeComments`: (Optional) (Boolean) This will add all the comments that Imgur provides into the post objects. Please keep in mind that the time and resources the actor uses will increase proportionally to the number of comments.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to scrape over a specific list URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that is explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detailed requests. If the actor doesn't block very often it'll scrape 100 listings in 2 minutes with ~0.025-0.03 compute units.

### Imgur Scraper Input example

```json
{
    "startUrls": [
        "https://imgur.com/user/IsNice",
        "https://imgur.com/t/burrito",
        "https://imgur.com/gallery/ILtkgRA",
        "https://imgur.com/search?q=nice%20word"
    ],
    "search": "super meme",
    "includeComments": false,
    "proxy": {
        "useApifyProxy": true
    },
    "endPage": 5,
    "maxItems": 10
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## Imgur Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Imgur actor.

## Scraped Imgur Properties

The structure of each item in Imgur looks like this:

### Item Detail

```json
{
    "type": "post",
    "id": "JBTJqu2",
    "accountId": "22440270",
    "title": "holiday",
    "description": "",
    "numberOfViews": 8578,
    "numberOfUpvotes": 23,
    "numberOfDownvotes": 5,
    "numberOfPoints": 18,
    "numberOfImages": 1,
    "numberOfComments": 6,
    "numberOfFavorites": 1,
    "virality": 3475.255272505103,
    "score": 18.5435,
    "isInMostViral": false,
    "isAlbum": true,
    "isMature": false,
    "coverId": "dK9p4A1",
    "createdAt": "2019-07-13T03:20:56Z",
    "updatedAt": null,
    "url": "https://imgur.com/gallery/JBTJqu2",
    "platform": "api",
    "account": {
        "id": "22440270",
        "username": "IsNice",
        "avatarUrl": "https://i.imgur.com/YLvWS5K_d.png?maxwidth=290&fidelity=grand",
        "createdAt": "2015-07-19T10:05:29Z"
    },
    "tags": [
        "storytime",
        "funny",
        "awesome"
    ],
    "media": [
        {
            "mime_type": "video/mp4",
            "url": "https://i.imgur.com/dK9p4A1.mp4",
            "ext": "mp4",
            "width": 960,
            "height": 540,
            "size": 87699,
            "title": "",
            "description": "",
            "isAnimated": true,
            "isLooping": true,
            "duration": 9,
            "has_sound": false
        }
    ],
    "comments": [
        {
            "id": 1681576587,
            "parent_id": 0,
            "comment": "https://youtu.be/q-qqrGtlHkg",
            "account_id": 3708825,
            "post_id": "JBTJqu2",
            "upvote_count": 2,
            "downvote_count": 0,
            "point_count": 2,
            "vote": null,
            "platform_id": 4,
            "platform": "android",
            "created_at": "2019-07-13T03:45:15Z",
            "updated_at": "2019-07-13T04:05:31Z",
            "deleted_at": null,
            "next": null,
            "comments": [
                {
                    "id": 1681616815,
                    "parent_id": 1681576587,
                    "comment": "http://i.imgur.com/D5veJQj.gif",
                    "account_id": 85975675,
                    "post_id": "JBTJqu2",
                    "upvote_count": 2,
                    "downvote_count": 0,
                    "point_count": 2,
                    "vote": null,
                    "platform_id": 4,
                    "platform": "android",
                    "created_at": "2019-07-13T05:28:37Z",
                    "updated_at": "2019-07-13T18:44:25Z",
                    "deleted_at": null,
                    "next": null,
                    "comments": []
                }
            ]
        }
    ]
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
