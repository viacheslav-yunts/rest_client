# rest_client

Armtek HTTP клиент для работы с веб-сервисами (JSON или XML).

## Установка

## Примеры использования

### GET

#### Вызов без параметров

```php

	$response = HttpClient::get('component_name/component_method_name');

	// данные в исходном виде
	$response->content();

```

#### Вызов с параметрами

```php

	$request = [
		'url' => 'component_name/component_method_name',
		'params' => [

			'id'     => '12350ME1D',
			'lang'   => 'en-us',
			'format' => 'rss_200'
		]
	];

	$response = HttpClient::get($request);

	// данные в исходном виде
	$response->content();

	// в формате json
	$response->json();

	// в формате XML
	$response->xml();

```

### POST

```php

	$request = [
		'url' => 'component_name/component_method_name',
		'params' => [

			'id'     => '12350ME1D',
			'lang'   => 'en-us',
			'format' => 'rss_200'
		]
	];

	$response = HttpClient::post($request);

	// ответ в исходном виде
	$response->content();

	// в формате json
	$response->json();

	// в формате XML
	$response->xml();
```

### Изменение заголовков запроса

```php
$response = HttpClient::get([
	'url' => 'http://some.where.url',
	'headers' => ['Connection: close', 'Authorization: some-secret-here']
]);

// Заголовки
$response->headers();
```
