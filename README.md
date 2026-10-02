# WriteAlt for Joomla

Native Joomla administrator component for generating accessible alt text and optimizing local article images in place.

## Requirements

- Joomla 5.0 or later (Joomla 6 supported)
- PHP 8.1 or later
- PHP cURL and GD extensions enabled
- Articles containing local images under the Joomla `/images` directory
- A WriteAlt API key

## Installation

1. In Joomla administrator, open **System -> Install -> Extensions**.
2. Upload `pkg_writealt-1.0.16.zip`.
3. Open **Components -> WriteAlt**.

## Getting started

1. Get your API key at <https://writealt.com/dashboard#settings/ap>.
2. In **Components -> WriteAlt**, paste your API key, choose the optimization threshold, and select **Save settings**.
3. Select **Refresh images**. The package enables **Content - WriteAlt article integration** automatically, and WriteAlt lists local images found in article intro text, full text, and the native Intro/Full Images fields.
4. In an article's **Images and Links** tab, select an image and click **Generate with WriteAlt** beside its native alt-text field. Save the article to persist the generated description.
5. In the WriteAlt component you can also use **Generate alt text** and **Optimize image** on a single image, or the bulk actions for all images.

## Data and privacy

The API key is stored in this Joomla site's `com_writealt` component configuration. It is sent only from the Joomla server to WriteAlt over HTTPS. Image URLs are sent to WriteAlt only when an authorized Joomla administrator requests generation. Alt text is written back to the article containing the image. Optimization replaces the existing file in place and does not create a duplicate.

## Updates

The package registers a Joomla update server (`updates.xml` in this repository), so new releases appear under **System -> Update -> Extensions**.

## License

GNU General Public License version 2 or later. See [LICENSE](LICENSE).
