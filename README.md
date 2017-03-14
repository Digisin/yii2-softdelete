# Yii2 Soft Delete

Soft delete behavior for Yii2.


## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
$ composer require digisin/yii2-softdelete "*"
```

or add

```
"digisin/yii2-softdelete": "*"
```

to the `require` section of your `composer.json` file.


## Usage

In your ActiveRecord class:

```php
public function behaviors() {
    return [
        \digisin\softdelete\SoftDeleteBehavior::className(),
        // or
        [
            'class' => \digisin\softdelete\SoftDeleteBehavior::className(),
            'attribute' => 'deleted_time',
            'value' => new \yii\db\Expression('NOW()'), // for sqlite use - new \yii\db\Expression("date('now')")
        ],
    ];
}
```

In your ActiveQuery class:

```php
public function behaviors() {
    return [
        \digisin\softdelete\SoftDeleteQueryBehavior::className(),
        // or
        [
            'class' => \digisin\softdelete\SoftDeleteQueryBehavior::className(),
            'attribute' => 'deleted_time',
        ],
    ];
}
```
