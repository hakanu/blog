---
published: true
layout: post
category: selfhost
title: Bulk delete assets (images and videos) from Immich
---
![](https://devdala.wordpress.com/wp-content/uploads/2025/08/image.jpg)

My reddit thread: https://www.reddit.com/r/immich/comments/1n1ewfa/is_there_a_way_to_move_assets_from_one_user_to/

TL;DR: I messed up while importing a big library into immich and need to roll this back somehow.

I've a semi large immich setup (5tb) with 2 users. I mistakenly uploaded around 500GB of assets into other user's account instead of my own account due to my messup of the API keys through immich-go.

I was wondering if there is a clean approach to fix the ownership issue instead of deleting everything and starting over. [Apparently not](https://www.reddit.com/r/immich/comments/1ifabvo/help_moving_assets_from_one_user_to_another/)

I thought about doing something like this but I was not sure if the physical files can stay under /upload/user2_id while owner is user1_id and what that would mean for other sub components for immich:

```sql
UPDATE "asset" SET "ownerId" = 'user1\_id' WHERE "ownerId" = 'user2\_id' AND "createdAt" >= '2025-08-26';
Any opinions on the above solution? Gemini recommends to run storage migration afterwards but my storage templates don't seem enabled in the settings anyways.
```

Apparently, it's somewhat possible but not everything will work without additional work in the db and possibly moving physical files according to the [reddit Immich community](https://www.reddit.com/r/immich/comments/1n1ewfa/is_there_a_way_to_move_assets_from_one_user_to/), huge thanks!

Then I had to go for safer path by deleting the assets from the other account then reupload. Surprise, this is not easy either. Most of the info online is outdated, I don't see "Recently uploaded" button anymore in the UI; Date based search is not giving  the exact images I uploaded. So what can i do?

Let's pull the asset ids from the db into a file since i know how to do it:

```bash
docker exec immich_postgres psql -U $DB_USERNAME -d $DB_NAME -c "SELECT * FROM assets WHERE \"ownerId\" = '$OWNER_ID' AND \"createdAt\" >= '2025-08-26';" > asset_ids_to_be_deleted.txt
```

Then I need some python power to read this file and call immich asset deletion endpoint through the api. ofc you can do that from curl too

<script src="https://gist.github.com/hakanu/ff51ea5620c8a1603afdb1a339018c19.js"></script>

Tricky part is setting the batch size to 1; I tried with multiple numbers, nothing worked even though api response is 200, the assets are not deleted.

```sql
SELECT count(*) FROM assets WHERE "ownerId" = '$OWNER_ID' AND "createdAt" >= '2025-08-26';
```