Sortable GridView Widget for Yii2
========================
Sortable modification of Kartik GridView widget.

[![Packagist](https://img.shields.io/packagist/dt/naduvko/yii2-sortable-grid-view-widget.svg)] [![Packagist](https://img.shields.io/packagist/v/naduvko/yii2-sortable-grid-view-widget.svg)] [![license](https://img.shields.io/badge/License-MIT-yellow.svg)]

Installation
------------
The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

* Either run

```
php composer.phar require --prefer-dist "naduvko/yii2-sortable-grid-view-widget" "*"
```

or add

```json
"naduvko/yii2-sortable-grid-view-widget" : "*"
```

to the `require` section of your application's `composer.json` file.

* Add to your database new `unsigned int` attribute, such `sortOrder`.

* Add new behavior in the AR model, for example:

```php
use himiklab\sortablegrid\SortableGridBehavior;

public function behaviors()
{
    return [
        'sort' => [
            'class' => SortableGridBehavior::className(),
            'sortableAttribute' => 'sortOrder'
        ],
    ];
}
```

* Add action in the controller, for example:

```php
use himiklab\sortablegrid\SortableGridAction;

public function actions()
{
    return [
        'sort' => [
            'class' => SortableGridAction::className(),
            'modelName' => Model::className(),
        ],
    ];
}
```

Usage
-----
* Use SortableGridView as standard GridView with `sortableAction` option.
You can also subscribe to the JS event 'sortableSuccess' generated widget after a successful sorting.
