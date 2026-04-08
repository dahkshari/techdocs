# Boardgames

Contains information about tabletop board games, including types, estimated time to finish, number of required players, and appropriate age. It also provides titles of similar games for each response.

## Endpoints

 **GET  boardgames/{gameId}**

Gets description information for a specific board game ID.

## Parameters

### Path parameters

| Path parameter | Description |
| :---- | :---- |
| {gameId} | Value that identifies the board game you want to look up. Valid {gameId} values are available on our site someboardgame.com. |

### Query string parameters

| Query string parameter | Required/Optional | Description | Type |
| :---- | :---- | :---- | :---- |
| showSimilar | Optional | Number of similar games to include in the response. Default is 1\. | Integer |

## Sample request

| curl \-X GET "https://api.someboardgame.com/data/1.5/boardgames?appid=APIKEY\&gameId=1234\&showSimilar=3" |
| :---- |

(In the above code, replace APIKEY with your actual API key.)

## Sample response

The following is a sample response from the boardgames/{gameId} endpoint:

| {     "boardgames": \[         {            "game": "Forbidden Island",            "type": "Cooperative",            "time": 30,            "players": {               "playersMin": 2,               "playersMax": 4            },            "age": 10,            "similar": "Pandemic, Spirit Island, Arkham Horror"         }     \] } |
| :---- |

### Response definitions

The following table describes each item in the response.

| Response item | Description | Data type |
| :---- | :---- | :---- |
| **game** | The game you selected based on the {gameId} in the request. The game name is listed on someboardgame.com database. | String |
| **type** | The type of game selected. See someboardgame.com/types for descriptions of each game type. | String |
| **time** | Estimated number of minutes to complete the game. | Integer |
| **players** | Minimum and maximum number of players required to play the game. | Object |
| **players/playersMin** | Minimum number of players required to play the game. | Integer |
| **players/playersMax** | Maximum suggested number of players to play the game. | Integer |
| **age** | Minimum suggested player age. | Integer |
| **similar** | Titles of games with the same type. The default is 1, but use the showSimilar query string parameter to include more. | String |

