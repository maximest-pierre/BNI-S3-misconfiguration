# Bonshaw Delivery Network S3 misconfiguration

**This misconfiguration has now been fix**

After ordering an item off of Amazon, we saw that the tracking was using a company Bonshaw Delivery Network. 

The page is just a generic order detail and tracking information. They added a picture as the proof of delivery. The picture is serve using an S3 bucket (https://bni-dist-app-delivery-img-prod.s3.amazonaws.com/). 

By going directly to the url, we can see the whole list of every item in the bucket. So if you pick any of them you can actually see any proof of delivery.

## Production Example 

Listing
https://bni-dist-app-delivery-img-prod.s3.amazonaws.com/

Example image
https://bni-dist-app-delivery-img-prod.s3.amazonaws.com/CAP3883801170336949504_out.jpg

## Development Enviroment
So we can see from the url that it's prod what happen if change it to dev.

We get another unsecured S3 bucket. There not a lot of image but the developper seems to like Cherry Coke Zero a lot.
### Dev Example 
Listing
https://bni-dist-app-delivery-img-dev.s3.amazonaws.com/

Example image
https://bni-dist-app-delivery-img-dev.s3.amazonaws.com/JPEG_20201208_111323_8059241219165990536.jpg

## Solution
Please just remove the listing on a public S3 bucket. This would make it a lot harder to find the correct url for each image.
