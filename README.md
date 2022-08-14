# Sample Implementation of LaunchDarkly 
This is a naive implementation of a vanilia Javascript utilizing several flags.

Setup instructions assume basic knowledge of LaunchDarkly and availabilty of a project

## Live Demo
A live demonstration can be viewed by browsing to my [Github page](https://bjpohl.github.io)

## LaunchDarkly Setup
### Segment Setup
1. Create a segment called "VowelStarters"
1. For targeting, add a rule that includes users whose name regex matches "^[a|e|i|o|u]"

### Feature Flag Setup
##### Special Users
1. Create a feature flag called, "SpecialUsers"
2. For targeting, add a rule where:
* User is in segment VowelStarters AND
* anonymous is false
3. Default rule is false
4. Leave variations as default

##### Text Color Feature
1. Create a feature flag called, "TextColorFeature"
2. Variations type: String, three variations:
* Black
* Blue
* Red
3. Two rules for targeting:
* Rule 1:
   * anonymous is false AND
   * User is in segment VowelStarters
   * Serve Blue
* Rule 2
   * anonymous is false AND
   * User in not in segment VowelStarters
   * Serve Black
4. Default Rule: Percentage Rollout
* 33.3 for two variations, 33.4 for other

Ensure both feature flags are ON

Ensure both feature flags are available for "SDKs using client-side ID"

### Client Application Setup
You can either clone this repository in its entirity and edit the "index.html" page. 

OR

Download/copy the content of [the index page](https://raw.githubusercontent.com/bjpohl/bjpohl.github.io/main/index.html).

Edit the page and replace the clientID variable on line 15 with your client id from the applicable client-side id from your environment.

Open the edited file in any modern browser.
