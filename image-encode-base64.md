```php

<?php
// Encode
$data = base64_encode(file_get_contents($file['uploaded_file']['tmp_name']));
$data = 'data: ' . mime_content_type($file['uploaded_file']['tmp_name']) . ';base64,' . $data;
$this->data['uploaded_file'] = $data;
$this->data['uploaded_file_mime_info'] = 'data: ' . mime_content_type($file['uploaded_file']['tmp_name']) . ';base64,';
$this->data['uploaded_file_mime'] = mime_content_type($file['uploaded_file']['tmp_name']);
```
