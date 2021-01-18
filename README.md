# PHP Common Exceptions

[![SensioLabs Insight](https://img.shields.io/sensiolabs/i/36a9a695-37c5-4836-bd15-33a0d03ee915.svg)](https://insight.sensiolabs.com/projects/36a9a695-37c5-4836-bd15-33a0d03ee915)
[![Code Climate](https://codeclimate.com/github/chroma-x/php-common-exceptions/badges/gpa.svg)](https://codeclimate.com/github/chroma-x/php-common-exceptions)
[![Latest Stable Version](https://poser.pugx.org/chroma-x/common-exceptions/v/stable)](https://packagist.org/packages/chroma-x/common-exceptions)
[![Total Downloads](https://poser.pugx.org/chroma-x/common-exceptions/downloads)](https://packagist.org/packages/chroma-x/common-exceptions)
[![License](https://poser.pugx.org/chroma-x/common-exceptions/license)](https://packagist.org/packages/chroma-x/common-exceptions)

A PHP library providing common exception classes used by different projects.

## Installation

```{json}
{
   	"require": {
        "chroma-x/common-exceptions": "~3.0"
    }
}
```

## Usage

### Autoloading and namesapce

```{php}  
require_once('path/to/vendor/autoload.php');
```

---

### Handling exceptions

#### Catching by concrete class

```{php}
try{
	// Perform something maybe throwing an exception
} catch (ChromaX\CommonException\NetworkException\ConnectionException $exception) {
	// API is not reachable
} catch (ChromaX\CommonException\NetworkException\CurlException $exception) {
	// Curl failed
} catch (ChromaX\CommonException\ApiException\InvalidResponseException $exception) {
	// API returns an unexpected result
} catch (ChromaX\CommonException\ApiException\RequestQuotaException $exception) {
	// API requests over the allowed limit
} catch (ChromaX\CommonException\ApiException\NoResultsException $exception) {
	// API request had no result
} catch (ChromaX\CommonException\IoException\FileWriteException $exception) {
	// Log file was not writable
}

```

#### Catching by parent class

```{php}
try{
	// Perform something maybe throwing an exception
} catch (ChromaX\CommonException\NetworkException\Base\NetworkException $exception) {
	// Any network exception was thrown
} catch (ChromaX\CommonException\ApiException\Base\ApiException $exception) {
	// Any API exception was thrown
} catch (ChromaX\CommonException\IoException\Base\IoException $exception) {
	// Any IO exception was thrown
}

```

#### Catching by grand parent class

```{php}
try{
	// Perform something maybe throwing an exception
} catch (ChromaX\CommonException\Base\BaseException $exception) {
	// Any exception was thrown
} 

```

## Contribution

Contributing to our projects is always very appreciated.  
**But: please follow the contribution guidelines written down in the [CONTRIBUTING.md](https://github.com/chroma-x/php-common-exceptions/blob/master/CONTRIBUTING.md) document.**

## License

PHP Common Exceptions is under the MIT license.
