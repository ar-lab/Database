# Database Class

Simple PHP Database class based on mysqli

## Installation

```php
require_once ('Database.php');
```

## Initialization

```php
$dbHost = 'localhost';
$dbName = 'phonebook';
$dbUser = 'root';
$dbPass = '';

$db = new Database($dbHost, $dbName, $dbUser, $dbPass);
```

## Usage

### Select

```php
$db->select('contacts', 'id, name, phone, email');

$data = $db->getData();
```

### Select Row

```php
$db->select('contacts', 'id, name, phone, email', ['id' => 1]);

$data = $db->getDataRow();
```

### Select Column

```php
$db->select('contacts', 'name', null, ['name' => 'ASC']);

$data = $db->getDataCol();
```

### Select Cell

```php
$db->select('contacts', 'name', ['id' => 1]);

$data = $db->getDataCell();
```

### Insert

```php
$data = [
    'name'  => 'Jack',
    'phone' => '1234567890',
    'email' => 'jack@mail.com',
];

$db->insert('contacts', $data);

$contactId = $db->getInsertId();
```

### Update

```php
$data = [
    'name'  => 'Jack Simpson',
    'phone' => '1234567890',
    'email' => 'jack@mail.com',
];

$db->update('contacts', $data, ['id' => $contactId]);
```

### Delete

```php
$db->delete('contacts', ['id' => $contactId]);
```
