# Store

## Usage

```php
require_once 'Store.php';

$store = new Store('./store', ['prettify' => true]);

// You can use $store('users') just like an array
$store('users')[] = [
	'name' => 'Adam',
    'age' => 36
];

foreach ($store('users') as $user) {
	var_dump($user);
}

// Although some array functions don't work on it, like count(...)
// But I use the inbuilt ArrayObject, so you can do this:
$num = $store('users')->count();

// If you want to set/get all data at once, you can use the data property:
$allUsers = $store('users')->data;
$store('users')->data = [];
```