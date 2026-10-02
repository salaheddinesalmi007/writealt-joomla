# WriteAlt for Joomla

Native Joomla administrator component for generating accessible alt text and optimizing local article images in place.

## Requirements

- Joomla 5.0 or later (Joomla 6 supported)
- PHP 8.1 or later
- PHP cURL and GD extensions enabled
- Articles containing local images under the Joomla `/images` directory
- A WriteAlt API key for each Joomla site owner

## Install for testing

1. In Joomla administrator, open **System -> Install -> Extensions**.
2. Upload `pkg_writealt-1.0.16.zip`.
3. Open **Components -> WriteAlt**.
4. Paste the site owner's WriteAlt API key, choose the optimization threshold, and select **Save settings**.
5. Select **Refresh images**. The package enables **Content - WriteAlt article integration** automatically and WriteAlt will list local images found in article intro text, full text, and native Intro/Full Images fields.
6. In an article's **Images and Links** tab, select an image and click **Generate with WriteAlt** beside its native alt-text field. Save the article to persist the generated description.
8. Test one image first with **Generate alt text** and **Optimize image**. Then test the bulk actions.
9. Confirm the generated alt attribute by opening the article editor and viewing the image HTML. Confirm optimization by comparing the file size in the card and the file under `/images`.

## Data and privacy

The API key is stored in this Joomla site's `com_writealt` component configuration. It is sent only from the Joomla server to WriteAlt over HTTPS. Image URLs are sent to WriteAlt only when an authorized Joomla administrator requests generation. Alt text is written back to the article containing the image. Optimization replaces the existing file in place and does not create a duplicate.

## Updates

The package registers a Joomla update server (`updates.xml` in this repository), so new releases appear under **System -> Update -> Extensions**.

## Packaging for release

The ZIP must contain `com_writealt.xml` at its root. Do not zip the parent `joomla` directory itself. Increase the version in `com_writealt.xml` and the output filename for every release.

## Publishing checklist

- Test installation and upgrade on a clean Joomla 5 and Joomla 6 site.
- Test an article with JPG, PNG, and WebP images.
- Test missing and existing alt text.
- Test a user without `core.manage` access.
- Verify PHP cURL and GD are available on the production host.
- Provide this README as the installation/user guide and publish the extension under the GPL-2.0-or-later license.
