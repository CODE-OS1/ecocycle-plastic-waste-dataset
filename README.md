# EcoCycle Plastic Waste Dataset

An open-source photo dataset of plastic waste found in Ghana, labeled by plastic type, to train AI models that identify recyclable materials in the local context.

The dataset is built by the community: anyone can photograph plastic waste and contribute. It powers the material recognition in the **EcoCycle** app, where users scan plastic waste, see what it's worth, and schedule pickups with collectors in their neighbourhood.

## Why this dataset

Most public waste datasets (such as TACO and TrashNet) are made up of European and American packaging. Plastic waste in Ghana looks different: water sachets, local drink bottles, gallons, foam food packs. Models trained elsewhere often get these wrong. This dataset fills that gap.

## Contribute photos

📸 **[Submit photos through the form](https://docs.google.com/forms/d/e/1FAIpQLSerptF-LPuwH_KUmGWakYUDvpv4HESC5c4FeYwwp8QnCjW9lQ/viewform)** (takes about 2 minutes, needs a Google account)

No Google account? Send your photos on WhatsApp to **0205800935**.

**How to take a good photo**
- One item per photo, filling most of the frame
- Photograph it as you found it: dirty, crushed or with a label is fine
- If there's a recycling number (a triangle with 1–7), add a close-up of it
- No people, faces, house numbers or car plates in the shot

By contributing, you confirm you took the photos and agree to release them under CC BY 4.0.

## Classes

| Class | Resin code | Examples |
| --- | --- | --- |
| `pet_clear` | 1 | Clear water and soft drink bottles |
| `pet_coloured` | 1 | Green, blue or brown drink bottles |
| `ldpe_sachet` | 4 | Water sachets / pure water bags |
| `ldpe_film` | 4 | Shopping bags, wrappers, thin film |
| `hdpe` | 2 | Gallons, jerry cans, oil and detergent containers |
| `pp` | 5 | Cups, food containers, bottle caps, buckets, chairs |
| `ps_foam` | 6 | Foam food packs, takeaway boxes |
| `pvc` | 3 | Pipes, hard rigid plastic |
| `other` | 7 | Other plastics |
| `not_plastic` | – | Non-plastic items (used to teach the model to say no) |

## Dataset structure

```
data/
  images/
    img_000001.jpg
    img_000002.jpg
    ...
  metadata.csv
```

`metadata.csv` columns:

| Column | Description |
| --- | --- |
| `id` | Image ID, matches the file name |
| `verified_label` | Class confirmed by the review team |
| `contributor_label` | Class chosen by the contributor |
| `resin_code` | Recycling number on the item, if visible |
| `condition` | Clean, dirty, crushed, label on, cap on, faded |
| `colour` | Clear, white, coloured, mixed |
| `region` | Region of Ghana |
| `area` | Town or neighbourhood (no addresses) |
| `found_at` | Where the item was found |
| `date` | Date the photo was taken |
| `weight_kg` | Approximate weight, if known |
| `contributor` | Credit name, or "Anonymous contributor" |
| `license` | CC BY 4.0 |

## How photos are processed

Every submission goes through review before it is published:

1. Location metadata (GPS/EXIF) is removed from every image
2. Duplicate images are removed
3. A team member checks the label and confirms or corrects it
4. Blurry photos, photos with people, and non-relevant images are rejected
5. Approved images are added to the next release

## Releases

| Version | Date | Verified images | Notes |
| --- | --- | --- | --- |
| v0.1 | Coming soon | – | First public release |

## License

The photos and metadata in this dataset are licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](LICENSE).

You are free to use, share and adapt them, including commercially, as long as you give credit.

**How to cite:**

> EcoCycle Plastic Waste Dataset, CODE-OS1, 2026. https://github.com/CODE-OS1/ecocycle-plastic-waste-dataset. Licensed under CC BY 4.0.

## Contributors

Thank you to everyone who has contributed photos. Contributors are credited in [CONTRIBUTORS.md](CONTRIBUTORS.md) with each release.

## Contact

Questions or want to run a photo drive with your school, club or community group? Open an issue or reach us at **codeos285@gmail.com**.
