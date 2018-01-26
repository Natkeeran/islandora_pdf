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

#### 2.1 Creating the Fields
* Go to *Manage fields* of the new fedora resource type: `/admin/structure/types/manage/islandora_porcus_object/fields`
* Add a new description field (Text (plain, long))
* Add a new field with *Reference type* `Other`
* Chose *Type of item to reference* as Media
* Select the `Default` *Reference method* and `PORCUS_TEXT` as the *Bundles*

#### 2.2 Form Display
* Go to *Manage form* display: `admin/structure/types/manage/islandora_porcus_object/form-display`
* Specify the porcus_text field's *WIDGET* as `Inline entity form - complex`
* Click the gear icon for the porcus_text field and set *Form mode* as `inline`.

#### 2.3 View Display
* Go to *Manage form* display: `admin/structure/types/manage/islandora_porcus_object/display`
* Specify the porcus_text field's *Format* as `Rendered entity`

### 3 - Create RDF Mapping for the bunldes (islandora_porcus_object and PORCUS_TEXT)
* Adopt and modify an existing RDF Mapping such as `https://github.com/Islandora-CLAW/islandora_image/blob/8.x-1.x/config/install/rdf.mapping.fedora_resource.islandora_image.yml` to create the RDF mapping of the target bundle
* Go to the form to import a single configuration: `/admin/config/development/configuration/single/import`
* Select *Configuration type* RDF mapping and import the mapping
* Repeat it for the other bundle

### 4 - Exporting config and creating a module
* It is easier to use Drupal's [feature](https://www.drupal.org/project/features) module to export all the config of a content type.  Please see this [doc](https://github.com/Islandora-CLAW/CLAW/blob/master/docs/islandora/drupal-bundle-configurations.md) for further informaiton about the configurations that need to be exported.
* Delete the islandora_porcus_object.features.yml file 
* Copy and update 'composer.json', `*.info.yml', '*.module' files from islandora_image.  



