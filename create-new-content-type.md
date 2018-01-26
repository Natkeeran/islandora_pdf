## Introduction
This is a demo module for Islandora CLAW. It illustrates the modeling of a content type and creation of a drupal module for CLAW.

## Steps to create claw_porcus
### 1 - Create a new Media bundle
* Go to `/admin/structure/media/add`
* Provide a *Label* to the bundle: `PORCUS_TEXT`
* Leave the *Type provider* as `Generic media`
* Go to the *Manage fields* of the new media bundle: `/admin/structure/media/manage/porcus_text/fields`
* Add the existing `field_file` field to the bundle.

### 2 - Create a new Node bundle/content type
* Go to `admin/structure/types`
* Click the *Add Content type* button to create a new Fedora resource bundle
* Provide a *Label* to the fedora resource type: `Islandora Porcus Object`
* Go to *Manage fields* of the new fedora resource type: `/admin/structure/types/manage/islandora_porcus_object/fields`
* Add a new description field (Text (plain, long))
* Add a new field with *Reference type* `Other`
* Chose *Type of item to reference* as Media
* Select the `Default` *Reference method* and `PORCUS_TEXT` as the *Bundles*
* Go to *Manage form* display: `admin/structure/types/manage/islandora_porcus_object/form-display`
* Specify the porcus_text field's *WIDGET* as `Inline entity form - complex`
* Click the gear icon for the porcus_text field and set *Form mode* as `inline`.
