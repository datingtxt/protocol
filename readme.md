# Dating.txt
Most dating services are terrible, users are on it for the wrong reasons, and people get spammed by misaligned incentives.

Proposed solution is `dating.txt`, you add some bio fields in `profile.json` and can also use the `proof of work` field to make all potential matches go through a challenge to make sure they are "worthy" (described in spec below). 

## Matching
We use the github fork api to see users on the protocol.

Use `https://api.github.com/repos/datingtxt/protocol/forks` to find a fork, and check their profiles, and if you find someone interesting you can contact them (note that they might require proof of work!!)

## Spec
| Field                     | Field description                                             | Format           |
| ------------------------- | ------------------------------------------------------------- | ---------------- |
| name                      | Your name                                                     | String           |
| gender                    | Your gender                                                   | String           |
| description               | Description of you                                            | String           |
| location                  | Location your are comfortable sharing (for instance the city) | String           |
| contact                   | For instance an webpage form, or `mailto:` URI                | URI              |
| proof of work.url"        | `URL` for the challenge                                       | URL, nullable    |
| proof of work.description | Description of the proof of work challenge                    | String, nullable |

To prevent spam, users can use the `proof of work` field to set a url for a "challenge". This challenge can be something basic as requiring a simple question so the users gets a UUID.
Note, if you use the `proof of work` field you should validate this in the `contact` uri, this can be done by for instance using a webpage form, or requiring it to be set in subject of an email.

## Disclaimer
This is partially a joke, but most dating apps are terrible, so this might actually be a good idea.

