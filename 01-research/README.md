# Reasearch on Twitter API

I have researched the github, twitter and spotify API recently. I am about to share my finding on these API's in this reasearch paper. 

## Github API

- They used nouns for representing resources. Also they used plural nouns to represent resource collections.
    - Example:
        - `/repos`
        - `/orgs`
        - `/repositories`
- They used singular nouns to represent individual resources.
    - Example:
        - `/user/starred`
- They used hierarchical structure for related resources
    - Example:
        - `/repos/{owner}/{repo}/branches/{branch}`
- They used both `_` (underscore) and `-` (hyphen) to separate the words.
    - Example
        - `/users/{username}/received_events`
        - `/orgs/{org}/actions/runners/registration-token`
- They didn't used any file extensions in the URL.
- We have to use `X-GitHub-Api-Version` header to specify the api version.
- They used authentication by sending a token in the `Authorization` header of the request.
- They used `GET` methods to get something, `POST` to create something, `PUT` to replace something, `PATCH` to update a specific part and `DELETE` to delete something.

## Twitter API

- They used nouns for representing resources. Also they used plural nouns to represent resource collections.
    - Example:
        - `/statuses`
        - `/friends`
        - `/users`
        - `/followers`
- They used singular nouns to represent individual resources.
    - Example:
        - `/statuses/retweet/:id`
- They used hierarchical structure for related resources
    - Example:
        - `/statuses/retweet/:id`
- They used `_` (underscore) to separate the words.
    - Example
        - `/statuses/retweets_of_me`
- They didn't used any file extensions in the URL.
- They versioned their API. For the Twitter API v2 they used `/2/users`.
- They used the following methods for authentication.
    - OAuth 1.0a
    - OAuth 2.0
    - Basic authentication
- I found only `GET` and `POST` methods for CRUD operations. There is no usage of `DELETE`, `PUT` or `PATCH`. They used `POST` method to destroy. Which is I think a bad pracice.

## Spotify API

- They used nouns for representing resources. Also they used plural nouns to represent resource collections.
    - Example:
        - `/albums`
        - `/playlists`
        - `/artists`
        - `/chapters`
- They used singular nouns to represent individual resources.
    - Example:
        - `/albums/{id}`
        - `/chapters/{id}`
- They used hierarchical structure for related resources
    - Example:
        - `/playlists/{playlist_id}/followers`
        - `/shows/{id}/episodes`
- They didn't used any file extensions in the URL.
- They versioned their API.
    - Example:
        - `/v1/playlists`
        - `/v1/albums`
- They used authentication by sending a token in the `Authorization` header of the request.
- They used `GET`, `POST`, `PUT` and `DELETE` methods for CRUD operations.

## My comments

By researching these three API's I think Spotify API followed the best practices of API design from every aspects.