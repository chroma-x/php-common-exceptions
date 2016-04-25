# PHP Common Exceptions

[![Code Climate](https://codeclimate.com/github/markenwerk/php-common-exceptions/badges/gpa.svg)](https://codeclimate.com/github/markenwerk/php-common-exceptions)
[![Latest Stable Version](https://poser.pugx.org/markenwerk/common-exceptions/v/stable)](https://packagist.org/packages/markenwerk/common-exceptions)
[![Total Downloads](https://poser.pugx.org/markenwerk/common-exceptions/downloads)](https://packagist.org/packages/markenwerk/common-exceptions)
[![License](https://poser.pugx.org/markenwerk/common-exceptions/license)](https://packagist.org/packages/markenwerk/common-exceptions)

A PHP library to query Google's Places service for querying locations and addresses and getting details by Places ID.

## Installation

```{json}
{
   	"require": {
        "markenwerk/common-exceptions": "~1.0"
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
} catch (CommonException\ApiException\NetworkException $exception) {
	// API is not reachable or curl failed
} catch (CommonException\ApiException\ApiException $exception) {
	// API returns an unexpected result
} catch (CommonException\ApiException\ApiLimitException $exception) {
	// API requests over the allowed limit
} catch (CommonException\ApiException\ApiNoResultsException $exception) {
	// API request had no result
} catch (CommonException\IoException\FileWriteException $exception) {
	// Log file was not writable
}

```

#### Catching by parent class

```{php}
try{
	// Perform something maybe throwing an exception
} catch (CommonException\ApiException\Base\BaseException $exception) {
	// Any API exception was thrown
} catch (CommonException\IoException\Base\BaseException $exception) {
	// Any IO exception was thrown
}

```

#### Catching by grand parent class

```{php}
try{
	// Perform something maybe throwing an exception
} catch (CommonException\Base\BaseException $exception) {
	// Any exception was thrown
} 

```

## Contribution

Contributing to our projects is always very appreciated.  
**But: please follow the contribution guidelines written down in the [CONTRIBUTING.md](https://github.com/markenwerk/php-common-exceptions/blob/master/CONTRIBUTING.md) document.**

## License

PHP Common Exceptions is under the MIT license.