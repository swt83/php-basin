# Basin

A PHP package for working w/ the Basin API.

## Install

Normal install via Composer.

## Usage

```php
use Travis\Basin;

// retreive data
$response = Basin::run('YOURAPIKEY', 'submissions', [
    'filter_by' => 'all',
    'page' => 1,
    'form_id' => 'YOURFORMID',
]);

// response
stdClass Object
(
    [submissions] => Array
        (
            [0] => stdClass Object
                (
                    [id] => 18734861
                    [payload_params] => stdClass Object
                        (
                            [utm_source] =>
                            [utm_medium] =>
                            [utm_campaign] =>
                            [email] => CENSORED
                            [first_name] => John
                        )

                    [form_id] => 123456
                    [spam] =>
                    [created_at] => 2022-09-10T19:01:18.659Z
                    [updated_at] => 2022-09-10T19:01:21.607Z
                    [read] =>
                    [trash] =>
                    [spam_reason] =>
                    [webhook_sent_at] =>
                    [attachments] => Array
                        (
                        )

                    [form] => stdClass Object
                        (
                            [name] => CENSORED
                            [uuid] => CENSORED
                        )

                )

        )

    [meta] => stdClass Object
        (
            [count] => 1
            [inbox_count] => 1
            [spam_count] => 38
            [trash_count] => 0
            [page] => 1
            [per_page] => 100
            [form_name] => CENSORED
        )

)

// submit data
$response = Basin::post('YOURWEBSITE.com', 'URLENDPOINT', [
    'first' => 'Joe',
    'last' => 'Shmoe',
    'email' => 'joeshmoe@foobar.net',
]);
```

See the [documentation](https://usebasin.com/docs/api) for more information.