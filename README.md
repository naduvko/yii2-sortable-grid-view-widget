Sortable GridView Widget for Yii2
========================
Sortable modification of Kartik GridView widget.

[![Total Downloads](https://poser.pugx.org/naduvko/yii2-sortable-grid-view-widget/downloads)](https://packagist.org/packages/naduvko/yii2-sortable-grid-view-widget)
[![Latest Stable Version](https://poser.pugx.org/naduvko/yii2-sortable-grid-view-widget/v/stable)](https://packagist.org/packages/naduvko/yii2-sortable-grid-view-widget)
[![License](https://poser.pugx.org/naduvko/yii2-sortable-grid-view-widget/license)](https://packagist.org/packages/naduvko/yii2-sortable-grid-view-widget)

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
use naduvko\sortablegrid\SortableGridBehavior;

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
use naduvko\sortablegrid\SortableGridAction;

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
