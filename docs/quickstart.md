# Quickstart guide

:::info List available kitchen ingredients within 5 minutes

Use our test kitchen to make your first API request within 5 minutes.

:::


What's for dinner's APIs track kitchen ingredients on-hand.

Use the output as input to your app&mdash;some ideas include:

- filtering recipes to show those that would work with ingredients on-hand
- health coaching
- share info with medical practitioners
- and more


## Requirements

- API credentials (use test credentials: `demo-test`).
- A `kitchenId` (use test kitchen id: `altman-family`).
- A command-line to run curl commands.

## Listing available kitchen ingredients

**Make this request from the command-line:**

```
curl -i -X "https://api.whatsfordinner.dev/ingredients/altman-family" \
  -H 'Authorization: Bearer xxxxxx-xxxx-xxxxxx-xxxxxx-xxxxxx
```

**Response**

```json
{
  "kitchen": "altman-family",
  "updatedAt": "2021-06-23T19:23:21Z",
  "paginationTotal": 4,
  "paginationLimit": 100,
  "paginationOffset": 0,
  "ingredients": [
    {
      "name": "nectarine",
      "quantity": 3,
      "unit": "pcs",
      "use_before": "2021-06-26T12:00:00Z"
    },
    {
      "name": "milk",
      "quantity": 0.5,
      "unit": "gallon",
      "use_before": "2021-06-26T12:00:00Z"
    },
    {
      "name": "ground beef",
      "quantity": 0.75,
      "unit": "lbs",
      "use_before": "2021-06-24T12:00:00Z"
    },
    {
      "name": "broccoli",
      "quantity": 2,
      "unit": "cups",
      "use_before": "2021-06-27T12:00:00Z"
    }
  ]
}
```

## Create an account

Create an account and retrieve your API credentials from your profile.

## Getting access to a kitchen

Get access to a kitchen by asking permission:

Someone may grant access to their kitchen.
They may subsequently revoke access to their kitchen.

You may also request access to their kitchen.
