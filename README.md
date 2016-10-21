# treevel

## Installation

1. Require this package in your composer.json file and run composer install (or run `composer require winponta/treevel` directly):

    "winponta/treevel": "0.*"

2. Run composer:

    `composer install`


## Using

Enable your models to be ready to handle tree hierarchy records, using one of the traits of the package (for now only Parent tree model is available).

### Parent tree model

Parent tree models are handled using `parent id` references.

#### Trait

    <?php
        ...
        class MyModel extends Eloquent {
            use \Winponta\Treevel\Traits\ParentTreeModel;

#### Default properties

##### Parent id references

The default field value used by the package to handle the reference to parent record is named `parent_id`, you can change this value by customizing the database field name your table/collection is using. Do this by overwriting the `$parentField` property:

    <?php
        ...
        class MyModel extends Eloquent {
            use \Winponta\Treevel\Traits\ParentTreeModel;

            protected $parentField = 'my_father_id';

##### Node level propertie

These properties controls the deep level of the node on the tree. The default field value used to handle this feature is named `node_level`, you can change this value by customizing the database field name your table/collection is using. Do this by overwriting the `$levelField` property:

    <?php
        ...
        class MyModel extends Eloquent {
            use \Winponta\Treevel\Traits\ParentTreeModel;

            protected $levelField = 'level';
