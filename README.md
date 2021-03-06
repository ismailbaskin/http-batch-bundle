### HttpBatchBundle
HttpBatchBundle is a plugin for symfony ,that implement multipart/batch method.This implementation uses sub requests.
### What is multipart/batch
Http multipart/batch is a format for packaging multiple HTTP requests in a single request. You can read this draft for more info: https://tools.ietf.org/id/draft-snell-http-batch-00.html

###### You can decrease you request count (especially on api) with HTTPBatchBundle.
### Installing HttpBatchBundle
The easiest way to install HttpBatchBundle is through composer.
```bash
composer require ideasoft/http-batch-bundle
```
Do not forget register to AppKernel.php
```php
$bundles = [
            ...
            new \Ideasoft\HttpBatchBundle\HttpBatchBundle()
        ];
```
Now lets configurate it!
### Configuration
##### Routing
Add a route for HttpBatchBundle like that to your routing.yml
```yml
http_batch:
    resource: "@HttpBatchBundle/Controller/"
    type:     annotation
```
#### Sevice Registration
Register HttpBatchBundle services. Add this line to your services.yml
```yml
imports:
    ...
    - { resource: "@HttpBatchBundle/Resources/config/services.yml" }
```
That's all. Now you can use http batch implementation on your symfony project.
You can test it with Postman or anything else.

### Do yuo need a multipart/batch client for php?
You're lucky! You can try
https://github.com/mustafaileri/http-batch-client
