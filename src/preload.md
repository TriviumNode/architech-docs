# Random Minter Preload

When preloading NFTs into a random minter, you can upload metadata from a CSV or JSON file.

## CSV Upload

Download the template [here](https://alpha.architech.zone/architech-template.csv) 

CSV files are easy to use and can be edited with most spreadsheet editors (including Microsoft Excel).

When uploading metadata with a CSV you can specify the following metadata fields:

- Image File Name
- NFT Name
- Description
- Traits (trait Type and Value)
- Royalty Payment Address
- Royalty Percentage

## JSON Upload

Download the template [here](https://alpha.architech.zone/architech-template.json) 

JSON files are useful for power users that want to generate their metadata preogramatically. JSON files can specify any field in the CW721 metadata spec.

```js
interface ArchitechMetadata {
  file_name?: string;
  name?: string;
  description?: string;
  attributes?: Trait[];
  royalty_payment_address?: string;
  royalty_percentage?: number;
  animation_url?: string;
  background_color?: string;
  external_url?: string;
  image?: string;
  image_data?: string;
  youtube_url?: string;
}

interface Trait {
  trait_type: string;
  value: string;
}
```
| :memo:        Most fields are optional |
|---------------------------------------|

| Field | Type | Description |
| ----- | ---- | ----------- |
| file_name | String | Name of the image file for this NFT.<br>**Required if 'image' is not specified.** |
| name | String | The name of the NFT. |
| description | String | A description of the NFT. |
| attributes | Array | An array of traits. |
| royalty_payment_address | String | Address to send royalty payments. |
| royalty_percentage | Number | Royalty percentage. E.g. '5' = 5% |
| animation_url | String | A URL to any multi-media attachments. |
| background_color | String | Color to display behind the image. E.g. '#FF00FF' |
| external_url | String | A URL to view the token. |
| image | String | URL to the NFT image.<br>**Required if 'file_name' is not specified.** |
| image_data | String | Raw SVG image data. |
| youtube_url | String | A URL to a related Youtube video. | 

## Uploading Images

After uploading a CSV or JSON file, you will be able to select the images for your NFT's. The image's file name should match the `file_name` specified in the CSV or JSON. You will be notified of any missing or extra images.

If you uploaded a JSON: This step is optional if the image URL was included in the `image` field.


## Preloading

Once metadata and all images have been selected, the Preload button will be available. 

Be aware that it may take several minutes for your images to upload after clicking Preload.

## Token IDs

Token ID's are generated automaticlly in ascending order. The first token minted will be Token ID 1, etc.

Keep this in mind when creating your metadata, naming an NFT `My NFT #2` won't have Token ID 2.