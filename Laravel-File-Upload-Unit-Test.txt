```php
<?php

namespace Tests\DataProvider\ACS;

use Illuminate\Http\Request;
use Symfony\Component\HttpFoundation\File\UploadedFile;

class AgeValidationDataProvider
{

    /**
     * Age validation by face
     *
     * @return array
     */
    public function byFace()
    {
        $_FILES = [
            'image' => [
                'name' => 'the-old-face.jpg',
                'type' => 'image/jpg',
                'tmp_name' => __DIR__ . '/_files/the-old-face.jpg',
                'error' => 0,
                'size' => 20000,
            ],
        ];

        $uploadedFile = new UploadedFile($_FILES['image']['tmp_name'], $_FILES['image']['name']);
        $request = new Request();

        $request->files->set('image', $uploadedFile);

        return [
            array($request)
        ];
    }

    
}
```
