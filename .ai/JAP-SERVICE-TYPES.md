# JAP service types and order fields

This user-provided guide is host-specific context for TygerBooster. Use it with the selected JAP service row's `payload.type`, the handler's min/max/features, the current Service Builder capability snapshot, and the applicable ProductDefinition contract. Do not infer a service type or input shape from a marketing name.

Every JAP `add` request needs an API `key`, `action=add`, and the selected provider `service` ID. The fields below are additional inputs for the specified type. Required fields are listed for that order type; optional and conditional fields are identified separately. Always check the selected service's minimum, maximum, and available features.

Use the Builder's `chips/default` control for every input the JAP API expects as a newline-separated list. Set `defaults.textareaMode` to `true` and `defaults.separators` to `["Enter"]`. The host adapter must join chip values with newlines for the JAP request.

## General services

### Default

- Required: `link` (target page or post) and `quantity` (units to deliver).
- Optional drip feed: JAP accepts `runs` (number of deliveries) and `interval` (minutes between deliveries) when the selected service supports drip feed and the customer selects drip feed.
- In TygerBooster, the optional `Drip feed` toggle reveals both `runs` and `interval` and then requires both. `drip_feed` is a Builder control, not a JAP API field.

### Package

- Required: `link` (target page or post).
- JAP does not list a `quantity` input for this type. The TygerBooster product definition uses a fixed quantity of one internally.

### SEO

- Required: `link`, `quantity`, and `keywords`.
- Send `keywords` as a newline-separated list (`\n` or `\r\n`).

### Web Traffic

- Required: `link`, `quantity`, `country`, `device`, and `type_of_traffic`.
- `country` accepts a country code or full name, such as `US` or `United States`.
- `device` values: `1` Desktop, `2` Mobile (Android), `3` Mobile (iOS), `4` Mixed (Mobile), `5` Mixed (Mobile and Desktop).
- Conditional: `type_of_traffic=1` (Google Keyword) requires `google_keyword`; `type_of_traffic=2` (Custom Referrer) requires `referring_url`; `type_of_traffic=3` (Blank Referrer) requires neither.
- JAP's API also accepts optional `runs` and `interval` for drip feed. The current TygerBooster Web Traffic definition does not expose these fields; do not add them based on this guide alone.

## Comments and engagement

### Custom Comments

- Required: `link` and `comments` (one comment per line, separated by `\n` or `\r\n`).
- There is no separate JAP `quantity` field. The builder derives quantity from the number of comments.

### Custom Comments Package

- Required: `link` and `comments` (one comment per line, separated by `\n` or `\r\n`).
- There is no separate JAP `quantity` field. The builder uses the comments list for quantity and a fixed package quantity of one internally.

### Comment Likes

- Required: `link`, `quantity`, and `username` (the comment owner's username).

### Poll

- Required: `link`, `quantity`, and `answer_number` (the poll option to receive votes).

### Comment Replies

- Required: `link`, `username`, and `comments` (replies, one per line separated by `\n` or `\r\n`).
- There is no separate JAP `quantity` field. The builder derives quantity from the number of replies.

## Mentions

### Mentions with Hashtags

- Required: `link`, `quantity`, `usernames`, and `hashtags`.
- Send `usernames` and `hashtags` as newline-separated lists (`\n` or `\r\n`). TygerBooster also accepts commas and semicolons while collecting these lists.
- The SMM builder also accepts the type name `mentions` for this same field pattern.

### Mentions Custom List

- Required: `link` and `usernames` (a newline-separated list).
- There is no separate JAP `quantity` field. The builder derives quantity from the number of usernames.

### Mentions Hashtag

- Required: `link`, `quantity`, and `hashtag` (the hashtag used to find usernames).

### Mentions User Followers

- Required: `link`, `quantity`, and `username`.
- JAP describes `username` here as the URL from which followers are scraped; confirm the expected profile value for the selected service.

### Mentions Media Likers

- Required: `link`, `quantity`, and `media` (the media URL from which likers are scraped).

## Subscriptions

### Subscriptions

- Required: `username`, `min`, `max`, and `delay` (minutes). `min` and `max` are the quantity range for each new post.
- Optional: `posts` limits how many future posts are processed. Omitting it leaves the subscription unlimited.
- Optional when the service offers it: `old_posts` sets how many existing posts are processed.
- Optional: `expiry`, formatted `d/m/Y` (day/month/year).
- Allowed `delay` values: `0`, `5`, `10`, `15`, `20`, `30`, `40`, `50`, `60`, `90`, `120`, `150`, `180`, `210`, `240`, `270`, `300`, `360`, `420`, `480`, `540`, and `600`.
- The SMM builder also accepts the singular type name `subscription`.

## Group invites

### Invites from Groups

- Required: `link`, `quantity`, and `groups` (source groups, one per line separated by `\n` or `\r\n`).

## Reference

The source guide points to the [JAP API reference](https://justanotherpanel.com/api). This local guide records the user-provided host-specific notes; verify current API behavior when the task depends on changes since the guide was supplied.
